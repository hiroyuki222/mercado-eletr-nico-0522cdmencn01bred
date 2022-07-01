# Aula 19 - Mesa de trabalho

[Versão PDF]()

[Código fonte](https://drive.google.com/file/d/1bCrsVgVnz0uLre_607MpgXb3E3U4pnlG/view?usp=sharing)

## Proposta 

Esperamos nessa atividade o aluno reconhecer as etapas de configuração de um projeto WPF seguindo o design MVVM utilizando a biblioteca [Calibur.Micro](https://www.nuget.org/packages/Caliburn.Micro).

## Instruções

Com base nas instruções a seguir:

1. Instale a dependência Calibur.Micro e configure o projeto

- [ ] Instale a depedência [Calibur.Micro](https://www.nuget.org/packages/Caliburn.Micro).

- [ ] Apague o arquivo `Main.xaml`

- [ ] No arquivo `App.xmal`,

    - [ ] Apague a o trecho de código `StartupUri="Main.xaml"`

    - [ ] Redirecione projeto para o arquivo de configuração `Bootstrapper`

    ```xaml
    <Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary>
                    <local:Bootstrapper x:Key="Bootstrapper" />
                </ResourceDictionary>
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Application.Resources>
    ```

- [ ] Crie o arquivo `Bootstrapper.cs`

    - [ ] Inicialize o projeto

    ```cs
    using System.Windows;
    using Caliburn.Micro;

    namespace Wpf.MVVM
    {
        public class Bootstrapper: BootstrapperBase
        {
            public Bootstrapper()
            {
                // Inicializa o projeto
                base.Initialize();
            }
        }
    }
    ```

    - [ ] Defina qual será o Controlador padrão

    ```cs
    using System.Windows;
    using Caliburn.Micro;

    namespace Wpf.MVVM
    {
        public class Bootstrapper: BootstrapperBase
        {
            public Bootstrapper()
            {
                base.Initialize();
            }

            protected override void OnStartup(object sender, StartupEventArgs e)
            {
                // Define qual será o Controlador padrão
                // Nota: O controlador MainViewModel ainda não foi criado nessa etapa.
                base.DisplayRootViewFor<MainViewModel>();
            }
        }
    }
    ```

- [ ] Crie um controlador para o arquivo `Bootstrapper.cs`

    - [ ] Crie uma pasta `ViewModels` 

    - [ ] Crie uma classe `MainViewModel` em `ViewModels`

    ```cs
    namespace Wpf.MVVM.ViewModels
    {
        public class ShellViewModel: Screen
        {
        }
    }
    ```

- [ ] Crie uma janela para o controlador `MainViewModel`

    - [ ] Crie uma pasta `Views`

    - [ ] Crie uma janela `MainView` em `Views`

    **Nota:** Não é necessário adicionar nenhum trecho de código, a biblioteca [Calibur.Micro](https://www.nuget.org/packages/Caliburn.Micro) se encarregará de reconhecer, a partir do nome do arquivo, qual é seu controlador, neste exemplo o `MainViewModel`.

    - [ ] Crie uma Grid com as definições a seguir:

    ```xaml
    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="20"/>
            <ColumnDefinition Width="auto"/>
            <ColumnDefinition Width="auto"/>
            <ColumnDefinition Width="auto"/>
            <ColumnDefinition Width="*"/>
            <ColumnDefinition Width="20"/>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition Height="20" />
            <RowDefinition Height="auto" />
            <RowDefinition Height="auto" />
            <RowDefinition Height="auto" />
            <RowDefinition Height="*" />
            <RowDefinition Height="20" />
        </Grid.RowDefinitions>
    </Grid>
    ```
    
    - [ ] Crie um componente `<TextBlock>`

        - [ ] Defina o posicionamento do componente `Grid.Row="1" Grid.Column="1"`

        - [ ] Defina que sua propriedade `Text` seja `{Binding Path=NomeCompleto, Mode=OneWay}`

    - [ ] Crie um componente `<TextBox>`

        - [ ] Defina o posicionamento do componente `Grid.Row="2" Grid.Column="1"`

        - [ ] Defina que o nome `x:Name="NomeCompleto"`

    - [ ] Vincule o componente no controlador `MainViewModel`

    ```cs
    using Caliburn.Micro;
    using Wpf.MVVM.Models;

    namespace Wpf.MVVM.ViewModels
    {
        public class ShellViewModel: Screen
        {

        private string nomeCompleto;

        public string NomeCompleto { 
            get { 
                return nomeCompleto; 
            } 
            set { 
                nomeCompleto = value; 
                // Observa se o atributo/instância FirstName recebeu alguma atualização.
                base.NotifyOfPropertyChange(() => NomeCompleto);
            } 
        }
    ```

- [ ] Depure o projeto


## Conclusão

Espero que tenha curtido revisar todos esses recursos necessários nessa solução com sua equipe. Na próxima aula abordaremos os fundamentos do Banco de dados Relacional. 
