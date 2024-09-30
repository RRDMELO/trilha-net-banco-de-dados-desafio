### 1 - Buscar o nome e ano dos filmes
``` SQL
SELECT
    Nome,
    Ano
FROM
    Filmes;
```

![RESULTADO DA SOLUÇÃO 1](./Imagens/SOLUCAO1.png)

### 2 - Buscar o nome e ano dos filmes, ordenados por ordem crescente pelo ano
``` SQL
SELECT
    Nome,
    Ano
FROM
    Filmes
ORDER BY
    Ano
```
![RESULTADO DA SOLUÇÃO 2](./Imagens/SOLUCAO2.png)

### 3 - Buscar pelo filme de volta para o futuro, trazendo o nome, ano e a duração
``` SQL
SELECT
    *
FROM
    Filmes
WHERE
    Nome = 'De Volta para o Futuro'
```
![RESULTADO DA SOLUÇÃO 3](./Imagens/SOLUCAO3.png)

### 4 - Buscar os filmes lançados em 1997
``` SQL
SELECT
    *
FROM
    Filmes
WHERE
    Ano = 1997
```
![RESULTADO DA SOLUÇÃO 4](./Imagens/SOLUCAO4.png)

### 5 - Buscar os filmes lançados APÓS o ano 2000
``` SQL
SELECT
    *
FROM
    Filmes
WHERE
    Ano > 2000
```
![RESULTADO DA SOLUÇÃO 5](./Imagens/SOLUCAO5.png)

### 6 - Buscar os filmes com a duracao maior que 100 e menor que 150, ordenando pela duracao em ordem crescente
``` SQL
SELECT
    *
FROM
    Filmes
WHERE
    Duracao > 100
    AND Duracao < 150
ORDER BY
    Duracao
```
![RESULTADO DA SOLUÇÃO 6](./Imagens/SOLUCAO6.png)


### 7 - Buscar a quantidade de filmes lançadas no ano, agrupando por ano, ordenando pela quantidade em ordem decrescente
``` SQL
SELECT
    Ano,
    Count(*) AS Quantidade
From
    Filmes
GROUP BY
    Ano
ORDER BY
    Quantidade DESC
```
![RESULTADO DA SOLUÇÃO 7](./Imagens/SOLUCAO7.png)

### 8 - Buscar os Atores do gênero masculino, retornando o PrimeiroNome, UltimoNome
``` SQL
SELECT
    PrimeiroNome,
    UltimoNome
FROM
    Atores
WHERE
    Genero = 'M'
```
![RESULTADO DA SOLUÇÃO 8](./Imagens/SOLUCAO8.png)

### 9 - Buscar os Atores do gênero feminino, retornando o PrimeiroNome, UltimoNome, e ordenando pelo PrimeiroNome
``` SQL
SELECT
    PrimeiroNome,
    UltimoNome
FROM
    Atores
WHERE
    Genero = 'F'
ORDER BY
    PrimeiroNome
```
![RESULTADO DA SOLUÇÃO 9](./Imagens/SOLUCAO9.png)

### 10 - Buscar o nome do filme e o gênero
``` SQL
SELECT
    Nome,
    Generos.Genero
FROM
    Filmes
    INNER JOIN FilmesGenero ON Filmes.Id = FilmesGenero.IdFilme
    INNER JOIN Generos ON FilmesGenero.IdGenero = Generos.Id
```
![RESULTADO DA SOLUÇÃO 10](./Imagens/SOLUCAO10.png)


### 11 - Buscar o nome do filme e o gênero do tipo "Mistério"
``` SQL
SELECT
    Nome,
    Generos.Genero AS Genero
FROM
    Filmes
    INNER JOIN FilmesGenero ON Filmes.Id = FilmesGenero.IdFilme
    INNER JOIN Generos ON FilmesGenero.IdGenero = Generos.Id
WHERE
    Genero = 'Mistério'
```
![RESULTADO DA SOLUÇÃO 11](./Imagens/SOLUCAO11.png)


### 12 - Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel
``` SQL
SELECT
    Nome,
    Atores.PrimeiroNome,
    Atores.UltimoNome,
    ElencoFilme.Papel
FROM
    Filmes
    INNER JOIN ElencoFilme ON Filmes.Id = ElencoFilme.IdFilme
    INNER JOIN Atores ON ElencoFilme.IdAtor = Atores.Id
```
![RESULTADO DA SOLUÇÃO 12](./Imagens/SOLUCAO12.png)