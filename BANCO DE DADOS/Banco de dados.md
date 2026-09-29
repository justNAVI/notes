- Entrando no MariaDB/MySQL

```bash
sudo mariadb
```

# Bancos

## Exibindo Bancos

```sql
SHOW DATABASES;
```

# Criando usuário

- Necessário adicionar os privilégios que o usuário tem

```sql
CREATE USER 'navi'@'localhost' IDENTIFIED BY 'senha';
GRANT ALL PRIVILEGES ON *.* TO 'navi'@'localhost';
FLUSH PRIVILEGES;
);
```

- CREATE USER -> Cria o usuário 'navi'@'localhost', que só terá acesso ao localhost
- IDENTIFIED BY -> Define a senha do usuário
- GRANT ALL PRIVILEGES ON . TO -> Garante que o usuário terá todos os privilégios em qualquer banco de dados e tabela 
- FLUSH PRIVILEGES -> Recarrega a tabela de permissões e incorpora os novos privilégios e usuários

## Usuário com acesso remoto

- Para que o usuário possa ter acesso remoto

```sql
CREATE USER 'navi'@'localhost' IDENTIFIED BY 'senha';
GRANT ALL PRIVILEGES ON *.* TO 'navi'@'%';
FLUSH PRIVILEGES;
);
```

- CREATE USER -> Cria o usuário 'navi'@'%', que terá acesso remotamente
- IDENTIFIED BY -> Define a senha do usuário
-  GRANT ALL PRIVILEGES ON . TO -> Garante que o usuário terá todos os privilégios em qualquer banco de dados e tabela remotamente
- FLUSH PRIVILEGES -> Recarrega a tabela de permissões e incorpora os novos privilégios e usuários


# Criando Bancos

```sql
CREATE DATABASE nomeDoBanco;
```
## Deletando Bancos

```sql
DROP DATABASE nomeDoBanco;
```
## Entrando nos Bancos

```sql
USE nomeDoBanco;
```


# Tipos de Dados

Utilizar o tipo de dado correto torna a performance do banco de dados melhor

- VARCHAR(100) -> String de 0 a 65k de caracteres
- TEXT(500) -> String de até 65k de bytes (Maior que o VARCHAR)
- INT -> Números inteiros
- BIGINT -> Números inteiros (Maior que o INT)
- DATE -> Datas (YYYY-MM-DD)

# Constrains

São regras adicionais que podem ser colocadas em conjunto aos dados

- NOTNULL -> Obrigatóriamente o campo tem que ser preenchido
- UNIQUE -> Valores tem que ser únicos
- NOTNULL UNIQUE -> O valor é obrigatório e tem que ser único
- PRIMARY KEY -> Identifica de forma única uma linha do banco de dados

# Tabelas

## Criando Tabelas

- Criando uma tabela no banco de dados

```sql
CREATE TABLE pokemon(
	nome VARCHAR(100),
	Pokedex INT
);
```

## Deletando Tabelas

- Deletando uma tabela no banco de dados

```sql
DROP TABLE nomeDaTabela;
);
```

## Adicionando coluna a tabela

```sql
ALTER TABLE pokemon
ADD tipo VARCHAR(300);
```

## Retirando coluna da tabela

```sql
ALTER TABLE pokemon
DROP treinador;
```

## Modificando coluna da tabela

```sql
ALTER TABLE pokemon
MODIFY COLUMN tipo VARCHAR(500);
```

## Inserindo coluna na tabela

```sql
INSERT INTO pokemon (nome, tipo) VALUES ("mimikyu", "fantasma e fada");
```
















## Primary Key

- Usada para identificar de forma única uma linha do banco de dados
- Só pode haver uma PRIMARY KEY por tabela

```sql
CREATE TABLE usuarios(
	nome VARCHAR(100),
	senha VARCHAR(8),
	id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY
);
```

- INT -> número inteiro
- UNSIGNED -> Sem sinal ou seja, somente números positivos e não nulos
- AUTO_INCREMENT -> Ele incrementa automaticamente de 1 em 1 
- PRIMARY KEY -> Identifica que é uma chave primária única

