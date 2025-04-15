[Questão - 1](tarefa01-q01.sql)

[Questão - 4](tarefa01-q04.sql)

[Questão - 7](tarefa01-q07.sql)

[Questão - 10](tarefa01-q10.sql)

[Questão - 13](tarefa01-q13.sql)

# NATURAL JOIN e CROSS JOIN

## NATURAL JOIN
Um `NATURAL JOIN` combina as tabelas baseando-se automaticamente em colunas com nomes iguais em ambas. Não é necessário especificar manualmente a relação, já que o PostgreSQL faz essa correspondência automaticamente.

### Exemplo
```sql
CREATE TABLE clientes (
    id INT,
    nome VARCHAR(50)
);

CREATE TABLE pedidos (
    id INT,
    descricao VARCHAR(50)
);

-- Combinar as tabelas usando NATURAL JOIN
SELECT * 
FROM clientes 
NATURAL JOIN pedidos;
```

Neste exemplo, a junção será feita automaticamente pela coluna id, desde que ela exista em ambas as tabelas.

## CROSS JOIN
Um CROSS JOIN combina todas as linhas de uma tabela com todas as linhas de outra, gerando o produto cartesiano entre elas.

### Exemplo
```sql
CREATE TABLE produtos (
    nome VARCHAR(50),
    preco DECIMAL
);

CREATE TABLE categorias (
    categoria VARCHAR(50)
);

-- Realizar um CROSS JOIN
SELECT * 
FROM produtos 
CROSS JOIN categorias;
```
Se produtos tiver 3 linhas e categorias tiver 2, o resultado terá 6 linhas.

## Windows Functions no PostgreSQL
As Windows Functions são usadas para realizar cálculos baseados em um conjunto de linhas relacionado à linha atual, sem reduzir os resultados da consulta. Isso é útil para criar rankings, somatórios acumulativos, médias móveis, etc.

### Exemplo de utilização
```sql
SELECT nome, 
       salario,
       RANK() OVER (ORDER BY salario DESC) AS ranking
FROM funcionarios;
```
Aqui, a função RANK() gera um ranking dos funcionários com base no salário, mas sem agrupar os dados.
