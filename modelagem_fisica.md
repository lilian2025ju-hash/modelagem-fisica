## Banco de dados Microblog

## criação do banco de dados

```sql
CREATE DATABASE microblog CHARACTER SET utf8mb4;
```

```sql
 -- CRIANDO TABELA DO USÚARIOS
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY NOT NULL,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL,
    tipo ENUM ('editor','admim') NOT NULL
);
```

```sql

--CRIANDO TABELA CATEGORIAS
CREATE TABLE categorias (
 id INT AUTO_INCREMENT PRIMARY KEY NOT NULL,
 nome VARCHAR(100) NOT NULL

);




```