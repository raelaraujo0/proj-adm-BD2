SELECT p.nome AS projeto, p.data_inicio AS data_inicio_projeto, p.data_fim AS data_fim_projeto,
       a.nome AS atividade, a.data_inicio AS data_inicio_atividade, a.data_fim AS data_fim_atividade
FROM projeto p
JOIN atividade_projeto ap ON p.codigo = ap.cod_projeto
JOIN atividade a ON ap.cod_atividade = a.codigo
WHERE a.data_inicio < p.data_inicio OR a.data_fim > p.data_fim;
