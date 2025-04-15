SELECT f.nome
FROM funcionario f
WHERE f.salario > (
    SELECT salario
    FROM funcionario
    WHERE cod_depto = 2
    LIMIT 1
);
