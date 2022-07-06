# Aula 22 - Banco de dados: Relacionamento

## Relacionamento entre tabelas

O conceito de relacionamento dentro dos bancos de dados relacionais nada mais é do que a associação estabelecida entre registros por meio do apontamento de chaves entre suas tabelas.

Por exemplo, no diagrama de entidade relacionamento abaixo, você percebe que a tabela de contato possui relacionamento com a tabela de endereço. 

***Diagrama de Entidade Relacionamento (DER, ER, EER)** - É um diagrama que expressa visualmente a arquitetura de construção da estrutura do banco de dados. Este diagrama exibe cada tabela com suas colunas e seus tipos, bem como os relacionamentos existentes entre as várias tabelas.*

Nos bancos de dados relacionais os relacionamentos podem ser expressos em:

| Relacionamento | Descrição |
| --- | --- |
| 1:1 (um para um) | Ambas as tabelas podem ter somente um registro em cada lado do relacionamento.<br><br>Cada valor da chave primaria se liga a nenhum ou apenas um registro na tabela relacionada. | 
| 1:n (um para muitos) | A tabela com a chave primária contém somente um registro relacionada a nenhum, a um ou a muitos registros da tabela relacionada. |
| n:n (muitos para muitos) | Cada registro em ambas as tabelas pode se relacionar a nenhum ou a qualquer registro na tabela relacionada.<br><br>Neste caso uma terceira tabela é criada para gerenciar e armazenar os relacionamentos. Comumente chamada de tabela de associação.<br><br>Isto é necessário pois os bancos de dados relacionais não conseguem acomodar diretamente o relacionamento de muitos para muitos. |

### Chaves Primarias

Ao criar uma chave primária em uma tabela, ela identificará com exclusividade cada registro (linha) associada a esta chave. É importante realizar a correta modelagem arquitetural do banco a fim de identificar as colunas candidatas a chave ou definir uma coluna automática para tal.

Uma chave primária pode ser simples, ou composta.

**Chave simples:** Quando em sua criação é utilizada apenas uma coluna como referência primária.

**Chave composta:** Quando em sua criação é utilizada mais de uma coluna para compor a chave primária.

### Exemplo prático

**NULL e NOT NULL:** são comandos que dizem se é ou não permitido valores nulos nas colunas a que pertencem.

**IDENTITY:** é um recurso do T-SQL que permite em campos númericos o incremento automático. Você pode estipular o número inicial e a sequência para incremento desta forma: IDENTITY(1,2) ou seja, a sequência se inicia em 1 (um) e incrementa 2 (dois) a cada inserção.

**CONSTRAINT:** indica que uma restrição (regra) será inserida nos casos que foram utilizados note que auxiliou a criação da chave primaria da tabela endereço e da chave estrangeira do relacionamento entre endereço e contato.

**PRIMARY KEY:** comando utilizado para impor a chave primaria de uma tabela.

**FOREIGN KEY:**  comando utilizado para criar as chaves de relacionamento entre tabelas. Note que ele é utilizado junto do comando REFERENCES.