# Referência de comandos SQL para modelagem Física


## criação do banco de dados


```sql
CREATE DATABASE flybynight CHARACTER SET utf8mb4;
```

## Criação de tabela fornecedor

```sql
CREATE TABLE fornecedores(
    id INT  PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL

);
```
## Criação da tabela produtos

```sql
CREATE TABLE produtos(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR (100) NOT NULL,
    descricao TEXT, -- COMO É OPCIONAL , COLOCAMOS NULL OU OMITIMOS
    preco DECIMAL(10, 2) NOT NULL,
    quantidade INT NOT NULL,
    fornecedor_id INT NOT NULL,
    
    -- configurando a chave estrangeira fornecedor_id
    -- que se conecta (referencia) a chave primária id na tabela fornecedores
    FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)


);
```
## Criação de tabela fornecedor

```sql
CREATE TABLE lojas(
    id INT  PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL

);
```

## Criação de tabela lojas_produtos
nesta tabela, é necessário **dois relacionamentos**, um apontando para **produtos** e outro apontando para **lojas**.

```sql
CREATE TABLE lojas_produtos(
    loja_id INT NOT NULL,
    produto_id INT NOT NULL,
    estoque INT NOT NULL,

    -- Definindo a chave primária COMPOSTA
    PRIMARY KEY(loja_id, produto_id),

   -- Criando as Fks apontando par AS PHKS de cada tabela
    
    
    -- Regras para consistência nas operações de estoque
    -- Se uma loja for excluída, os estoque dela também serão
     FOREIGN KEY (loja_id) REFERENCES lojas (id), ON DELETE CASCADE,
    
   -- 2) Ao tentar excluir um produto, o banco deve impedir a exclusão
    FOREIGN KEY (produto_id) REFERENCES produtos (id) ON DELETE RESTRICT


);
```
