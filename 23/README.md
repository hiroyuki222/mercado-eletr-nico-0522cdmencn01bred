# Aula 23 - Banco de dados: Manipulando dados
## DML - Data Manipulation Language (Linguagem de Manipulação de Dados)

Na DML temos as definições das linguagens SQL para manipular nossos registros em banco de dados. Quando nos referimos a manipulação estamos falando das operações de Seleção (SELEC), Deleção (DELETE), Inserção (INSERT) e Atualização (UPDATE).

Após termos definido a estrutura de nosso banco de dados por meio dos comandos DDL utilizados na seção anterior. Nesta seção iremos trabalhar com os dados (registros) em nosso banco de dados.

### INSERT

```sql
INSERT INTO tabela(coluna1, coluna2, coluna3) 
VALUES ('valor1', valor2, 'valor3');
```

O Comando INSERT é responsável por inserir registros em uma tabela do banco de dados. É um comando simples sua sintaxe é:

- [ ] Inserir Registros nas nossas tabelas.

**Nota:** Quando queremos inserir mais de um registro com uma única instrução INSERT basta colocar "," (vírgula) e declarar os valores tal como o nosso exemplo abaixo. Observe como está sendo inserido.

```sql
INSERT INTO contato (nome, apelido, email_principal, sexo, data_nascimento)
VALUES ('John Doe', null, 'john@gmail.com', 'M', CONVERT(DATE,'1993-04-20')),
('Jane Doe', null, 'jane@gmail.com', 'F', CONVERT(DATE,'1978-08-21')),
('Maria Betânia', null, 'maria.b@gmail.com', 'F', CONVERT(DATE,'1949-12-01')),
('Paulo Augusto', null, 'paulo.augusto@outlook.com', 'M', CONVERT(DATE,'1966-12-19')),
('José Linhares', 'zé', 'ze@outlook.com', 'M', CONVERT(DATE,'2000-01-09')),
('Mônica', 'moniquinha', 'monicab@yahoo.com', 'F', CONVERT(DATE,'1998-08-21')),
('Magali', 'maga', 'magali@gmail.com', 'F', CONVERT(DATE,'1997-06-04')),
('Cebola Acelga', 'cebolinha', 'cebola@gmail.com', 'M', CONVERT(DATE,'1999-08-02')),
('Isabella Furtado', null, 'bella@yahoo.com', 'F', CONVERT(DATE,'1993-10-05')),
('Cascão Suginho', 'cascao', 'cascao@gmail.com', 'M', CONVERT(DATE,'1997-01-01'));
```

### SELECT

```sql
SELECT colunas FROM tabela
```

O comando SELECT é responsável por realizar as famosas consultas ao banco de dados. Por meio dele recuperamos os registros que temos disponíveis em nossa base de dados. E também conseguimos realizar condições de busca, agrupamento e ordenação. É possível atender qualquer necessidade de consulta por meio do SELECT e seus comandos adicionais.

```sql
SELECT * FROM contato;
SELECT nome, sexo, data_nascimento FROM contato;
```

### WHERE

```sql
SELECT colunas FROM tabela WHERE condicao
```

O WHERE especifica as condições de busca para o retorno de uma consulta.

```sql
SELECT * 
  FROM contato 
 WHERE nome like 'Joh%';
 
SELECT * 
  FROM contato 
 WHERE sexo = 'F' AND apelido IS NOT NULL
```

Abaixo temos um guia com os operadores mais utilizados na criação de condições lógicas nas consultas:

**Lógico**

AND: Operador utilizado para combinar duas expressões lógicas e retorna TRUE quando ambas as expressões forem TRUE.

SELECT * FROM contato WHERE apelido NOT IS NULL AND sexo = 'M'

OR: Operador avalia qualquer uma das expressões lógicas dentro da condição. Ou seja, quando qualquer valor retornar TRUE, mesmo que em suas expressões algum resultado seja false se ao menos um resultado encontrado for TRUE esse será o valor retornado.

SELECT * FROM contato WHERE sexo = 'F' OR apelido IS NULL;

IN: Quando este operador é utilizado ele avalia a existência de valores em uma subconsulta ou uma lista.

SELECT id, nome FROM endereco WHERE id IN (SELECT id FROM contato)

LIKE: É utilizado na comparação de caracteres (string). Neste guia iremos apresentar dois operadores curinga para o LIKE aprimorar mais o seu trabalho de comparação:

`SELECT * FROM contato nome like 'Cebola Acelga'`

- % (porcentagem): Este operador quando especificado procura a cadeia de caracteres e o que o sucede ou precede.
  - Procura pelo conjunto de caracteres DOE precedido por qualquer cadeia de outros caracteres: SELECT * FROM contato nome like '%DOE'
  - Procura pelo conjunto de caracteres especificados sucedidos por qualquer cadeia de outros caracteres: SELECT * FROM contato WHERE nome LIKE 'J%'
  - Procura pelo conjunto de caracteres em qualquer posição encontrada: SELECT * FROM contato WHERE nome LIKE '%li%'
- _ (sublinhado): Procura por qualquer caractere único:
  - Busca em um conjunto de 6 caracteres nomes terminados em 'li': `SELECT * FROM contato WHERE nome LIKE '____li'`

BETWEEN: Neste operador lógico podemos especificar um intervalo de valor a ser testado: `SELECT * FROM contato WHERE data_nascimento BETWEEN '1995-01-01' AND '1999-01-01'`

NOT: Realiza a negação de uma expressão lógica a ser avaliada.

`SELECT * FROM contato WHERE data_nascimento NOT BETWEEN '1995-01-01' AND '1999-01-01'`

`SELECT * FROM contato WHERE nome NOT LIKE 'J%'`

**Comparação**

Os operadores de comparação são:

| Operador | Significado |
| --- | --- |
| = (Igual a) | Igual a (Pode ser utilizado com string, mas, de preferência ao LIKE) |
| > (Maior que) | Maior que |
| < (Menor que) | Menor que |
| >= (Maior ou igual a) | Maior ou igual a |
| <= (Menor ou igual a) | Menor ou igual a |
| <> (Diferente de) | É diferente de (Pode ser utilizado com string, mas, de preferência `LIKE`) |

### Condição ORDER BY

```sql
SELECT * FROM contato ORDER BY id DESC
```

Este comando ordena o resultado da consulta. Você pode ordernar do menor para o maior (DESC) ou do maior para o menor (ASC).

*DESC = DESCENDING<br>
ASC = ASCENDING*

**Nota:** Quando utilizado, `ORDER BY` sempre será colocado no final da consulta!

### Funções de Agregador

As funções de Agregação são utilizadas para para realizar um cálculo em um conjunto de valores e retornarem um valor.

Nota: `COUNT` é uma função de agregação que não ignora valores nulos.

`COUNT`: retorna a contagem de registros na consulta. Pode ser utilizado com alguns parâmetros veja abaixo:

- `ALL`: Retorna a contagem de todos os registros sem distinção. Ignora se os valores são nulos ou duplicados. `SELECT COUNT(*) FROM contato`;

- `DISTINCT`: Retorna a contagem de apelidos distintos. `SELECT COUNT(DISTINCT apelido) FROM contato`;

- `EXPRESSION`: Retorna a contagem de apelidos eliminando valores nulos. `SELECT COUNT(apelido) FROM contato;`

### Comando UPDATE

```sql
UPDATE tabela 
  SET coluna1 = 'novo_valor', coluna2 = 3 
WHERE id = id_do_registro;
```

O comando `UPDATE` é responsável por realizar atualizações (edição) de dados. Também é possível utilizar os comandos de condição `WHERE` para filtrar as atualizações que estamos inserindo nos registros.

**Nota:** Tome cuidado ao realizar uma instrução de UPDATE. As atualizações de registros em banco de dados sempre devem utilizar as condições WHERE. A menos que seja uma situação muito específica que requeira alguma atualização geral de registros.

**Nota:** É comum nas atualizações utilizarmos os ids (chave primária) do registro que está sendo atualizado.

Nós vamos atualizar alguns dos nossos registros!

```sql
--Atualizar o Registro da Mônica, inserindo seu Sobrenome e corrigindo o e-mail
UPDATE contato
   SET nome = 'Mônica Dentuça', email_principal = 'monica@yahoo.com'
 WHERE nome = 'Mônica' AND apelido = 'moniquinha' AND email_principal = 'monicab@yahoo.com';
```

### DELETE

```sql
DELETE FROM tabela WHERE condicao;
```

O comando DELETE é quem irá fazer a exclusão de registros de nosso banco de dados. 

`DELETE` é um comando perigoso uma vez que a exclusão de dados é irreversível. Por tanto nunca execute sem o `WHERE`. A deleção de um registro normalmente obedece a uma ou mais condições.

```sql
DELETE FROM contato 
 WHERE nome LIKE 'Isabella Furtado' 
   AND email_principal LIKE 'bella@yahoo.com';
```