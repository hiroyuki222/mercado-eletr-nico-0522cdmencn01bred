# Aula 21 - Introdução à banco de dados

## O que é um Banco de Dados?


Vamos começar entendendo sobre Banco de Dados com conceitos práticos e rudimentares do nosso dia-a-dia!

Sabe aquela sua agenda de contatos telefônicos (isso é se você ainda utilizar né ). Então pensa nela! Uma lista com dados que juntos compõe uma informação. Essa coleção de dados como por exemplo Nome, Número de Telefone, Endereço estão escritas em um papel. Isso por si só já é um banco de dados! 

Por estarem escritas em papel esta é uma forma analógica de banco de dados (dados que não estão armazenados em meios computacionais).

Agora quando, resolvemos utilizar meios computacionais para guarda-los chegamos à definição abaixo de banco de dados:

**Nota: ** Uma coleção organizada de informações (dados) armazenadas eletronicamente em um sistema computacional.


## Sistema de Gerenciamento de Banco de Dados (SGBD)

***DBMS** - Data Base Management System*

Uma vez que a tendência de um banco de dados é crescer, assim se tornando mais oneroso o seu gerenciamento, facilitamos a gestão destes por meio dos BDMSs.

*Um DBMS é uma ferramenta responsável por facilitar as operações em um Banco de Dados. É um mecanismo pelo qual conseguimos organizar, acessar e manter a segurança dos dados descomplicando a complexidade de gerenciamento devido ao crescimento do banco de dados.*

## Tecnologia de Banco de Dados

Quando falamos em tecnologias de banco de dados estamos nos referindo à técnica de engenharia empregada na persistência dos dados nos dispositivos computacionais. Comercialmente temos hoje em dia duas grandes tecnologias com esta finalidade. São elas os **Banco de Dados Relacionais** e os **Banco de Dados NoSQL**.

**Persistir:** conservação ou armazenamento de um dado dentro de um mecanismo de armazenamento. Observa-se que na persistência de dados o dado é armazenado de forma a ser preservado garantindo assim sua integridade, confiabilidade e segurança.

## Tecnologia Relacional

A tecnologia de banco de dados relacionais foi a primeira a surgir nos adventos da computação moderna. Neste modelo os dados são armazenados em tabelas bidimensionais. Ou seja, a tabela possui um conjunto de registros guardados em linhas e colunas. Cada coluna representa um dado de uma informação registrada pela linha.

A consulta dos dados neste modelo é feita por uma linguagem denominada SQL - Structured Query Language - Linguagem de Consulta Estruturada.

Abaixo como é a disposição dos dados no modelo relacional. Mais à frente iremos ver especificidades deste modelo (este é nosso modelo alvo para os estudos).

| id | nome | ddd | celular |
| --- | --- | --- | --- |
| 1 | Beatriz Siqueira | 21 | 998700010 |
| 2 | Jorge Aragão | 21 | 985632100 |
| 3 | Fernanda Montenegro | 11 | 978452133 |

## Tecnologia NoSQL

A tecnologia NoSQL é uma tecnologia de banco de dados moderna criada para aumento de performance nas capacidades de leitura e gravação dos dados. Nesse modelo a informação é organizada em documentos e nós. 

Por exemplo o Mongo DB que é uma das mais famosas tecnologias de banco de dados NoSQL. Ele armazena os dados em documentos e a estrutura desses dados é muito semelhante ao JSON.

**JSON**: Acrônimo para **J**ava**S**cript **O**bject **N**otation.

```json
[{
	"nome": "Beatriz Siqueira",
	"ddd": 21,
	"celular": "998700010"
},
{
	"nome": "Jorge Aragão",
	"ddd": 31,
	"celular": "985632100"
},
{
	"nome": "Fernanda Montenegro",
	"ddd": 11,
	"celular": "978452133"
}]
```

## Diferenças entre as Tecnologias

### SQL (Relacional)

**Prós**

- [ ] Consultas Flexíveis: Suporta várias cargas de trabalho. Implementa a abstração de dados em registros tabulares permitindo que os motores de banco de dados otimizem as consultas.

- [ ] Compactação de dados: Devido à normalização e as otimizações, uma compactação maximiza o desempenho do banco de dados e o uso dos recursos.

- [ ] ACID: Atomicidade, Consistência, Isolamento e Durabilidade, garantem uma forte integridade dos dados fornecendo transações válidas.

**Contras**

- [ ] Rigidez de Modelo: Bancos relacionais requerem um extremo cuidado em sua modelagem. Por possuírem um esquema pré-definido suas alterações futuras podem se tornar um problema a ser contornado.


- [ ] Escalabilidade Horizontal Limitada: Expandir horizontalmente os bancos relacionais ou são imaturamente empregados, ou é completamente sem suporte ou são feitos por meio de tecnologias especificas e proprietárias (não existe um consenso de mercado sobre).

**Exemplos de Bancos de Dados**

- [ ] Db2

- [ ] MySQL

- [ ] Oracle

- [ ] Microsoft SQL Server

- [ ] Postgress

### NoSQL

**Prós**

- [ ] Escalabilidade e disponibilidade: Normalmente bancos NoSQL são projetados para suportar escalabilidade horizontal.

- [ ] Modelos Flexíveis: a não exigência do compromisso com o modelo de dados é um ponto forte. Uma vez que os esquemas são dinâmicos e podem ser alterados na hora.

- [ ] Alto Desempenho: Devido a uma limitação de funcionalidades é possível obter um alto desempenho nos bancos NoSQL.

- [ ] Abstração em alto nível: Os bancos de dados NoSQL fornecem APIs de alto nível para as operações que serão realizadas. Garantindo facilidade devido a abstração implementada por elas. 

**Exemplos de Bancos de Dados**

- [ ] Redis

- [ ] MongoDB

- [ ] CouchDB

- [ ] Cassandra

- [ ] Elasticsearch

## Microsoft SQL Server

O Microsoft SQL Server é um sistema de gerenciamento de banco de dados relacional desenvolvido pela Microsoft. Este **RDBMS** começou sua história no ano de 1989 já possuí 33 anos no mercado e sua evolução é constante até os dias de hoje.

O que distingue o MS SQL Server dos demais **DBMSs** é sua poderosa coleção de ferramentas gráficas que permitem operar com extrema facilidade a maioria dos recursos fornecidos por este banco de dados. Porém, mais do que ferramentas gráficas o SQL Server utiliza a linguagem SQL para realizar várias operações em banco de dados. Porém, saiba que o SQL implementado neste banco de dados sofreu uma carga de novas funcionalidades.

Devido a carga de todas as novas funcionalidades e recursos implementados pela Microsoft a linguagem passou a se chamar de **T-SQL** - Transactional SQL.

***RDBMS** - Relational DataBase Management System* 

***DBMS** - DataBase Management System*

Agora com os devidos conhecimentos iniciais iremos começar a explorar o universo dos bancos de dados.

### Instalar o SQL Server

- [ ] Acesse o link: [Download](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)

- [ ] Navegue até o fim da página e selecione a versão Express para download clicando no botão.

[IMG 1]

Baixar a Versão Express

[IMG 2]

Ao termino da instalação a tela abaixo será apresentada copie a **Cadeia de Conexão** e armazene para uso futuro. E clique na opção baixa o **SSMS**.

[IMG 3]

### Instalar o SQL Server Management Studio (SSMS)

- [ ] Acesse o link: [Download](https://aka.ms/ssmsfullsetup) 

- [ ] Após baixar, execute. A tela abaixo irá aparecer clique na opção **Install (Instalar)**

[IMG 4]

- [ ] Com o termino da instalação execute o aplicativo e vamos começar! (Busque pelo Microsoft SQL Server Management Studio)

[IMG 5]

Os acessos ao banco de dados sempre são controlados por login. Neste primeiro acesso iremos conectar ao banco de dados por meio da própria autenticação do Windows.

[IMG 6]

Em sequência a painel do SSMS irá carregar.

[IMG 7]

## T-SQL (Transition SQL)

Na linguagem SQL (T-SQL) temos definições bem claras dos recursos que serão disponibilizados nas operações de manipulação dos registros em banco de dados.

Vamos falar sobre elas logo abaixo:

### Tipos de Dados

No SQL Server cada coluna, variável local, expressão e parâmetro estão relacionados a um tipo de dados. Os tipos de dados mais comuns estão apresentados na lista abaixo.

**Nota:** Todos os comando do T-SQL são em inglês!

**Tipos númericos**

- bigint
- bit
- decimal
- int
- money
- numeric
- smallint
- smallmoney
- tinyint
- float
- real

**Data e hora**

- date
- datetime2
- datetime
- datetimeoffset
- smalldatetime
- time

**Caracteres (string)**

- nchar
- nvarchar
- ntext

**Binários**

- binary
- image
- varbinary

**Tipos Avançados**

- cursor
- hierarchyid
- sql_variant
- table
- etc...


## DDL

Na DDL temos os comandos da linguagem SQL para definir a estrutura (modelagem) em nosso banco de dados. Quando falamos de definição estamos nos referindo ao comando para criar (CREATE), para alterar (ALTER) e para deletar (DROP) um objeto da modelagem.

### CREATE

Por meio do comando CREATE é possível criar tanto uma nova tabela no modelo quanto o próprio esquema de banco de dados. Como sabemos uma tabela não existe sem um banco de dados então primeiro iremos executar a criação do nosso esquema de banco.

A sintaxe do comando CREATE é:

**Criar um banco**

```
CREATE DATABASE nomedobanco;
```

**Criar tabela**

```
CREATE TABLE nomedatabela(
    coluna1 TIPO [COMANDO],
    coluna2 TIPO [COMANDO],
    coluna3 TIPO [COMANDO]
)
```

**Nota:** O tipo pode ser um dos vários que já vimos na seção anterior. Já os comandos podem ser nenhum ou vários dos disponiveis iremos ver melhor os comandos mais a baixo. Mas saiba que os seguintes comandos podem ser aplicados: PRIMARY KEY, NOT NULL, NULL, IDENTITY, FOREIGN KEY, dentre outros.

### ALTER

O comando ALTER destina-se a realizar alterações na estrutura de um objeto do banco. Por exemplo em nossa tabela de endereço ficou ausente o campo para informar a cidade. Então teremos de incluir uma alteração na estrutura da tabela para receber este novo campo. E também vamos alterar a precisão do campo complemento que ficou pequena.

- [ ] Incluir coluna cidade.

```
ALTER TABLE endereco ADD cidade NVARCHAR(50) NULL;
```

- [ ] Alterar coluna complemento.

```
ALTER TABLE endereco ALTER COLUMN complemento NVARCHAR(20) NULL;
```

- [ ] Adicionar um novo relacionamento entre Endereco e UF.

```
ALTER TABLE endereco ADD CONSTRAINT FK_ENDERECO_UF FOREIGN KEY (id_uf) REFERENCES uf(id);
```