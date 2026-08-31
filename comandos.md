# Referência de comandos SQL para modelagem Física


## criação do banco de dados


```sql
CREATE DATABASE flybynight CHARACTER SET utf8mb4;
```

## Criação de tabela fornecedor

```sql
CREATE TABLE fornecedores(
    id INT  PRIMARY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL

);
```
