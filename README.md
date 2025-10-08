# Tipos-de-dados-e-regras-na-modelagem-SQL
Neste artigo será explicado os tipos de dados e regras na modelagem SQL, com exemplos para facilitar o entendimento do leitor.
Um banco de dados SQL (Structured Query Language) é um sistema utilizado para armazenar, organizar e gerenciar informações de forma estruturada. Ele é baseado em tabelas compostas por linhas (registros) e colunas (campos), permitindo que os dados sejam manipulados por meio de uma linguagem padronizada — o SQL.

Com o SQL, é possível criar estruturas de dados (modelagem), definir regras de integridade, consultar informações, atualizar registros e garantir a consistência dos dados ao longo do tempo.
Esses bancos de dados são amplamente utilizados em aplicações de todos os tipos — desde pequenos sistemas locais até grandes plataformas corporativas.

### Tipos de Dados de Texto no SQL
###  1.1) Caracteres:

| Tipo              | Descrição                                                                                                       | Uso Comum |
|------------------|------------------------------------------------------------------------------------------------------------------|-----------|
| `char`           | String de caracteres de tamanho fixo, máximo de 8000 caracteres.                                                 | Códigos, siglas, estados (ex: BR, SP) |
| `varchar`        | String de caracteres de tamanho variável, máximo de 8000 caracteres.                                             | Nomes, endereços, descrições |
| `nchar`          | Dados Unicode de tamanho fixo, máximo de 4000 caracteres.                                                        | Textos com caracteres especiais |
| `nvarchar`       | Dados Unicode de tamanho variável, máximo de 4000 caracteres.                                                    | Textos internacionais, multilíngues |
| `text`           | Cadeia de caracteres de tamanho variável. Até 2 GB de dados.                                                     | Artigos, comentários, logs |

### 1.2) Números Exatos:

| Tipo              | Descrição                                                                                          | Armazenamento                   | Uso Comum |
|------------------|----------------------------------------------------------------------------------------------------|---------------------------------|-----------|
| `bit`            | Valor booleano: 0, 1 ou NULL.                                                                      | -                            | Flags, indicadores de status |
| `decimal` / `numeric` | Valores exatos que permitem parte fracionária. De -10^38 + 1 a 10^38 - 1.                        | 5 a 17 bytes (dependendo da precisão) | Valores monetários ou científicos |
### 1.3) Numerais:

| Tipo              | Descrição                                                                                          | Armazenamento                   | Uso Comum |
|------------------|----------------------------------------------------------------------------------------------------|---------------------------------|-----------|
| `tinyint`        | Números inteiros de 0 a 255                                                                       | 1 byte                          | Contadores pequenos, códigos, classificações |
| `smallint`       | Números inteiros de -32.768 a 32.767                                                             | 2 bytes                         | Idades, pequenos estoques |
| `int`            | Números inteiros entre -2.147.483.648 e 2.147.483.647                                           | 4 bytes                         | IDs, quantidades, contadores |
| `bigint`         | Números inteiros entre -9.223.372.036.854.775.808 e 9.223.372.036.854.775.807                  | 8 bytes                         | Valores muito grandes, IDs globais |
| `real`           | Números de ponto flutuante entre -3,4 x 10^38 a 3,4 x 10^38 (precisão até 15 dígitos)           | 4 bytes                         | Valores aproximados de precisão moderada |
| `float`          | Números de ponto flutuante entre -1,79 x 10^308 a 1,79 x 10^308 (precisão até 34 dígitos)       | 8 bytes                         | Valores aproximados de alta precisão |
| `money`          | Dados monetários de -922.337.203.685.477,5808 até 922.337.203.685.477,5807                        | 8 bytes                         | Valores monetários |

### 1.4) Temporais:

| Tipo           | Formato                  | Intervalo                          | Precisão             | Armazenamento | Uso Comum |
|----------------|-------------------------|-----------------------------------|--------------------|---------------|-----------|
| `date`         | AAAA-MM-DD              | 0001/01/01 a 9999/12/31           | 1 dia              | 3 bytes       | Datas simples, como nascimento ou cadastro |
| `datetime`     | AAAA-MM-DD hh:mm:ss[.nnn]| 1753/01/01 a 9999/12/31          | 0,00333 segundos   | 8 bytes       | Datas com hora, como registros de transações ou logs |
| `smalldatetime`| AAAA-MM-DD              | 1900/01/01 a 2079/06/06           | 1 minuto           | 4 bytes       | Datas com hora em intervalos menores, como logs de eventos |
| `time`         | hh:mm:ss[.nnnnnnn]     | 00:00:00.0000000 a 23:59:59.9999999 | 100 nanossegundos | 3-5 bytes     | Somente horário, como horários de funcionamento ou agendamentos |

### Restrições no SQL
No SQL, uma constraint é uma regra aplicada a uma ou mais colunas de uma tabela para impor restrições aos dados que podem ser inseridos ou modificados.

Existem vários tipos de constraints no SQL, incluindo:

| Constraint       | Descrição                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------|
| `Primary Key`    | Garante a **unicidade** e a **não nulidade** de uma coluna ou conjunto de colunas. Identifica cada registro de forma única. |
| `Foreign Key`    | Estabelece uma **relação entre tabelas**, garantindo que os valores em uma coluna correspondam aos valores de outra tabela. |
| `Unique`         | Garante que os valores de uma coluna ou conjunto de colunas sejam **únicos** em uma tabela.                  |
| `Not Null`       | Garante que uma coluna **não possa conter valores nulos**.                                                   |
| `Check`          | Define uma **condição** que os valores de uma coluna devem atender.                                         |
| `Default`        | Define um **valor padrão** para a coluna quando nenhum valor for informado.                                  |

Essas constraints são usadas para impor integridade nos dados do banco de dados, com exceção da "default", garantindo que apenas valores válidos sejam armazenados nas tabelas e mantendo a consistência dos dados.

### Sugestão de materiais para consulta e aprendizado:
https://www.w3schools.com/sql/default.asp
https://kb.looplex.com.br/pt-BR/technical/common-data-model/legal-data-objects-and-complex-entities


### Fontes de referência:
https://www.dio.me/articles/restricoes-no-sql
https://docs.microsoft.com/pt-br/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-ver15


