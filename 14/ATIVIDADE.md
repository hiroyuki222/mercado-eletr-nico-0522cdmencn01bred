# Aula 14 - Mesa de trabalho

[Versão PDF](https://docs.google.com/document/d/1gna5yDeWieFfJMfE6xc2LJn1J9UcloBKNy-pe8yB-lE/edit?usp=sharing)

## Proposta 

Esperamos nessa atividade que o aluno compreenda os recursos de coleção e estimular a colaboração do grupo no processo de implementação de soluções utilizando a linguagem C#.

[Código fonte de apoio](https://drive.google.com/file/d/10qsg8yURoCSYXmQf3cb-T-OiG9tDKppJ)

### Instruções

1. Com base no código fonte:

- [ ] Crie uma classe abstrata para Administração.

    - [ ] Deve conter os seguintes métodos abstratos:

        - [ ] Cadastrar.

        - [ ] Remover.

    - [ ] Deve conter os seguintes métodos virtuais:

        - [ ] Atualizar cadastro.

        - [ ] Listar todos os inscritos.

- [ ] Crie uma classe para Aluno.

    - [ ] Implemente os seguintes atributos:

        - [ ] Matrícula.

        - [ ] Nome.

        - [ ] Sobrenome.

        - [ ] Telefone.

    **Notas:** Poderá armazenar apenas quatro valores.

    - [ ] Implemente os seguintes métodos públicos:

    - [ ] Atualizar cadastro.

    - [ ] Registrar nota - Deverá receber um número referente ao bimestre (1-4) e a nota (0-10);

    - [ ] Apresentar notas - Deverá apresentar todas as notas cadastradas por bimestre. Exemplo: 

    ```cs
        // 1 bimestre / nota 10
        // 2 bimestre / nota 5
        // 3 bimestre / nota 7
        // 4 bimestre / nota 6
    ```

    - [ ] Estágio do aluno - Aprovado ou Reprovado (true/false).

    - [ ] Média das notas.

- [ ] Crie uma classe para Curso que deverá herdar a classe abstrata Administração.

    - [ ] Implemente os seguintes métodos:

        - [ ] Cadastrar.

        - [ ] Remover.

    - [ ] Sobrescreva os seguintes métodos:

        - [ ] Atualizar cadastro.

        - [ ] Listar todos os inscritos.

2. Crie uma classe para Empresa que deverá herdar a classe abstrata Administração   

- [ ] Implemente os seguintes métodos:

    - [ ] Cadastrar.

    - [ ] Remover.

- [ ] Sobrescreva os seguintes métodos:

    - [ ] Atualizar cadastro.

    - [ ] Listar todos os inscritos.

- [ ] Crie uma classe para Funcionário.

    - [ ] Implemente os seguintes atributos:

        - [ ] Nome.

        - [ ] Sobrenome.

        - [ ] Telefone.

        - [ ] Salário.

        - [ ] CPF.

- [ ] Implemente os seguintes métodos:

- [ ] Estágio do Funcionário - Ativo ou Inativo (true/false).

## Conclusão

Espero que tenha curtido revisar todos esses recursos necessários nessa solução com sua equipe. Na próxima aula abordaremos o uso do [WPF](https://docs.microsoft.com/pt-br/dotnet/desktop/wpf/overview/?view=netdesktop-6.0). 
