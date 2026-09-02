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


```sql
--CRIANDO TABELA DE NOTÍCIAS
CREATE TABLE noticias (
id INT AUTO_INCREMENT PRIMARY KEY NOT NULL,

   titulo VARCHAR(100) NOT NULL,
   resumo TEXT NOT NULL,
   texto TEXT NOT NULL,
   imagem VARCHAR(100) NOT NULL,
   destaque ENUM('sim','nao') NOT NULL,
   data DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, --AUTOMATICAMENTE OBTER DATA/HORA 
   usuario_id INT NOT NULL,
  categoria_id INT NOT NULL,


);
```