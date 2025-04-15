-- Passo 1: Criando a view para contar os funcionários por departamento
CREATE VIEW total_funcionarios AS
SELECT cod_depto, COUNT(*) AS num_funcionarios
FROM funcionario
GROUP BY cod_depto;

-- Passo 2: Consulta principal
SELECT d.descricao AS departamento, 
       f.nome AS gerente, 
       COALESCE(t.num_funcionarios, 0) AS num_funcionarios
FROM departamento d
LEFT JOIN funcionario f ON d.cod_gerente = f.codigo
LEFT JOIN total_funcionarios t ON d.codigo = t.cod_depto;
