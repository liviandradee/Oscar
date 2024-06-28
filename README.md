# Oscar 🏆

### Quantas vezes Natalie Portman foi indicada ao Oscar?

SELECT * FROM indicados_ao_oscar WHERE nome_do_indicado = 'nathalie portman' 
return: 3

### Quantos Oscars Natalie Portman ganhou?
apenas 1

### Amy Adams já ganhou algum Oscar?

SELECT *
FROM indicados_ao_oscar
WHERE ano_cerimonia = 2024 AND vencedor = 'Sim';

### A série de filmes Toy Story ganhou um Oscar em quais anos?

UPDATE indicados_ao_oscar
SET vencedor = 'Sim'
WHERE ano_filmagem = %2024% AND categoria = nome_do_indicado = 'Toy Story';

### A partir de que ano que a categoria "Actress" deixa de existir? 

DELETE FROM indicados_ao_oscar
WHERE Actress = % ;


### O primeiro Oscar para melhor Atriz foi para quem? Em que ano?

SELECT nome_do_indicado, MIN(ano_filmagem)
FROM indicados_ao_oscar
WHERE categoria = 'Melhor Atriz' AND vencedor = 'Sim';
 
### Na coluna/campo "Vencedor", altere todos os valores com "Sim" para 1 e todos os valores "Não" para 0.

UPDATE indicados_ao_oscar
SET vencedor = CASE 
    WHEN vencedor = 'Sim' THEN 1
    WHEN vencedor = 'Não' THEN 0
    ELSE vencedor
END;

### Em qual edição do Oscar "Crash" concorreu ao Oscar?

SELECT DISTINCT cerimonia
FROM indicados_ao_oscar
WHERE nome_do_filme LIKE '%Crash%';


### Bom... dê um Oscar para um filme que merece muito, mas não ganhou.

INSERT INTO indicados_ao_oscar (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, nome_do_filme, vencedor)
VALUES (2023, 2024, 96, '%', 'Great Film', 'The Great Movie', 'Sim');


### O filme Central do Brasil aparece no Oscar? 

FROM indicados_ao_oscar
WHERE nome_do_filme LIKE '%Central do Brasil%';

### Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. 
INSERT INTO indicados_ao_oscar (ano_filmagem,  nome_do_filme, vencedor)
VALUES 
(1987, 'The Wolf of Wall Street', 'Não'),
(2002, 'Cidade de Deus', 'Não'),
(1998, 'Central do Brasil', 'Não');



###  Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?

SELECT nome_do_indicado, nome_do_filme, cerimonia
 
-- dar update p atualizar o database
FROM indicados_ao_oscar
 
WHERE categoria IN ('Uma Mente Brilhante', 'Jennifer Connelly', 'David Lean') AND ano_filmagem = 2002 AND vencedor = 'Sim';
tem menu de contexto





