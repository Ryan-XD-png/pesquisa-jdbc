# Projeto de Pesquisa (Geral) — DAO + JDBC

## O que é o padrão DAO (Data Access Object)

_____

## Ciclo de vida da conexão JDBC


_____

## Práticas de segurança

### Como funciona uma sql injection
Suponha que temos uma tabela de banco de dados chamada users que armazena dados de usuários do aplicativo. O userId é a coluna principal da tabela. Temos uma funcionalidade no aplicativo que permite obter informações por meio do userId. O valor do userId é recebido da solicitação do usuário.
```java
String userId = {get data from end user}; 
String sqlQuery = "select * from users where userId = " + userId;
```

com isso o invasor vai colocar no input onde coloca o id algo como 2 or 1=1

usando esse input a consulta vai ser select * from users where userId=2 or 1=1

Agora a consulta possui duas condições com a expressão SQL OR.

userId=2 : Esta parte corresponderá às linhas da tabela que têm o valor userId igual a '2'.

1=1 : Esta parte será sempre verdadeira. Portanto, a consulta retornará todas as linhas da tabela.

### Como previnir
A solução mais simples é usar um PreparedStatement para executar a consulta.

Em vez de concatenar o nome de usuário e a senha na consulta, nós os fornecemos para consulta por meio dos métodos setter do PreparedStatement.

Agora, os valores de nome de usuário e senha recebidos da solicitação são tratados apenas como dados, portanto, não ocorrerá injeção de SQL.

Uma ótima técnica é validar os dados antes de usá-los na consulta.

_____

## Fontes

- https://www.oracle.com/java/technologies/data-access-object.html 
- https://www.oracle.com/java/technologies/dataaccessobject.html
- https://docs.oracle.com/javase/tutorial/jdbc/basics/index.html
- https://docs.oracle.com/cd/E11035_01/wls100/server_start/server_life.html
- https://pt.stackoverflow.com/questions/113840/como-funciona-o-padr%C3%A3o-dao
- https://medium.com/@ajay.monga73/parameterized-queries-java-guide-how-to-prevent-sql-injection-with-parameterized-queries-10e250996df9 entender sql injection
- https://www.digitalocean.com/community/tutorials/sql-injection-in-java entender sql injection

_____

## Mapa conceitual

_____