# Aula 15 - Checkpoint

[Versão PDF]()

## Proposta 

Usando uma aplicação do tipo console do dotnet, criar uma aplicação que converterá o valor em reais (R$) para euro (€), iene (¥) e libra esterlina (£).

**Legenda**

- Real: moeda brasileira
- Dólar: moeda norte americana
- Euro: moeda europeia
- Iene: moeda japonesa
- Libra esterlina: moeda do Reino Unido

[Código fonte de apoio](https://drive.google.com/file/d/1pOus1sqx7oOpCNR82UQmcC8g8LSxbDyf/view?usp=sharing)

### Instruções

#### Novos conceitos ou funcionalidades desse exercício

Enum (Enumeration types) pode ser utilizado para controlar as moedas, estude como usar enumeradores no C#.
Usaremos nesse exercício a classe `System.Globalization.CultureInfo`. Você pode customizar a exibição do valor da moeda usando as conversões de string sem utilizá-la, mas o ideal é conhecer o `CultureInfo`, isso facilitará seu trabalho, então estude como formatar as moedas utilizando-a.
Estude também sobre os tipos mais indicados para moedas e qual o motivo. Durante o exercício dê preferência para o `decimal`, pois geralmente ele é o mais indicado na maioria das situações.
Lembre-se de utilizar os conceitos já utilizados nos exercícios anteriores.

**Estude:**
- Enumeration types.
- Classe `System.Globalization.CultureInfo`.
- Tipos `decimal`, `double`, `float`.
- Classe `Math`.
- Conversão de string para moedas.
- Conversões implícitas e explicitas.
- Documentação XML para C#.

#### Requisitos da aplicação

- Ao abrir a aplicação solicite o valor em real (R$) que o usuário deseja converter.

- Após leitura do valor a ser convertido, exibir um menu para selecionar para qual moeda o usuário deseja converter: dólar ($), euro (€), iene (¥) ou libra esterlina (£).

- Para realizar a conversão utilize os valore fictícios abaixo:
	- dólar ($) = R$ 4,50
	- euro (€) = R$ 6,20
	- iene (¥) = R$ 0,052
	- libra (£) = R$ 6,95

**Opcional**

- Fazer o controle de versionamento da sua aplicação usando Git;
- Subir a aplicação para um repositório do Github.
- Estude o uso de `Dictionary` e utilize-o para armazenar o valor de cada moeda que será usado na conversão.

### Desafios

1. Crie na sua aplicação a opção de converter as moedas dólar, euro, iene e libra esterlina em real.
2. Permita que o usuário informe qualquer uma das moedas (real , dólar, euro, iene ou libra esterlina) e depois converta pra qualquer uma das opções restantes.

### Prazo de entrega

**Sexta-feira** - 01/07/2022

## Conclusão

Espero que tenha curtido revisar todos esses recursos necessários nessa solução com sua equipe. Na próxima aula abordaremos o uso do [WPF](https://docs.microsoft.com/pt-br/dotnet/desktop/wpf/overview/?view=netdesktop-6.0). 
