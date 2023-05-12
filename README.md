

<p align="center" >
<br />
  <img src="https://aventurasnahistoria.uol.com.br/media/stories/oscar-2022-5-filmes-para-assistir-antes-da-premiacao/assets/4.gif" >
</p>

## 1- Quantas vezes Natalie Portman foi indicada ao Oscar?
R :3 vezes</br>
select count(*) from movies where `name` = "Natalie Portman" ;

## 2- Quantos Oscars Natalie Portman ganhou?
R: 1 Oscar</br>
select count(*) from movies where `name` = "Natalie Portman" and winner = "true";

## 3- Amy Adams já ganhou algum Oscar?
R: até então não ganhou nenhum</br>
select count(*) from movies where `name` = "Amy Adams" and winner = "true";

## 4- A série de filmes Toy Story ganhou um Oscar em quais anos?
R: 2011 e 2020</br>
select year_ceremony from movies where film like "%toy story%" and winner = "true";

## 5- Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?
R: A categoria melhor ator, com um total de 93 oscars. Melhor filme tem um total de 92</br>
select count(*) from movies where (category = 'actor' or category= "ACTOR IN A LEADING ROLE") and winner = 'true';

select count(*) FROM movies where (category = 'best picture' or category = 'best motion picture' or category = 'outstanding picture' or category = 'outstanding production' or category = 'outstanding motion picture' ) AND winner='true';


## 6- O primeiro Oscar para melhor Atriz foi para quem? Em que ano?
R: Janet Gaynor ganhou o oscar de melhor atriz no ano de 1928</br>
select `name`,year_ceremony from movies where category ="actress" and winner = "true";

## 7- Na coluna/campo Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.
update movies set winner="1" where winner = "true";</br>
update movies set winner="0" where winner = "false";

## 8- Em qual edição do Oscar "Crash" ganhou o prêmio principal?
R: na edição de número 78</br>
select ceremony from movies where film = "Crash" ;

## 9- Bom... dê um Oscar para um filme que merece muito, mas não ganhou.
R: Dei o premio de melhor filme ao "taxi driver", não desmerecendo Rocky pois gosto muito de ambos</br>
update movies set winner = "1" where id_movie = "5483"; 

## 10- O filme Central do Brasil aparece no Oscar?
R: não :(</br>
select film from movies where film like "%Central do Brasil%" ;


## 11- Inclua no banco 3 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem. 
R: inseri "fight club", "Scarface" e "Cidade de Deus"</br>
R:INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('1999', '2000', '72', 'BEST PICTURE', 'David Fincher', 'Fight club', '1');<br/>
 INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('1983', '1984', '56', 'ACTOR IN A LEADING ROLE', 'Al Pacino', 'Scarface', '1');<br/>
 INSERT INTO movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) VALUES ('2002', '2003', '75', 'BEST PICTURE', 'Fernando Meirelles', 'Cidade de Deus', '1');<br/>

## 12- Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.
R:Dei ao "Fight Club" o premio de "Best plot twist", ao "Scarface" o premio de "Clássico do gênero filme de gângster" e ao incrivel "Cidade de Deus" o premio de "Melhor filme brasileiro"</br>
update movies set category="Best plot twist" where id_movie =10396;</br>
update movies set category="Clássico do gênero filme de gângster" where film ="Scarface";</br>
update movies set category="Melhor filme brasileiro" where film ="Cidade de Deus";

## 13- Qual foi o primeiro ano a ter um prêmio do Oscar?
R: 1928</br>
select year_ceremony from movies

## 14 - Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?
R: O premio de melhor filme ficou com "Million Dollar Baby", melhor atriz com a "Hilary Swank", e melhor diretor com "Clint Eastwood" </br>
select * from movies where year_ceremony = 2005 and winner = "1" ;

## 15- Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.
R:INSERT INTO movies ( `name`) VALUES ('Aishwarya Rai Bachchan');</br>
INSERT INTO movies (`name`) VALUES ('Teo-neol');</br>
INSERT INTO movies (`name`) VALUES ( 'Saori Hayami');</br>
INSERT INTO movies ( `name`) VALUES ('Shin Min-a');</br>
INSERT INTO movies ( `name`) VALUES ('Junko Iwao');</br>
INSERT INTO movies (`name`) VALUES ('Rica Matsumoto');</br>
INSERT INTO movies (`name`) VALUES ('Priyanka Chopra');

## 16- Agora vamos falar da sua vida. Me diga o nome de uma pessoa que você admira e o que ela fez na sua vida. Agora me diz: Quê prêmio essa pessoa merece?
R: Aos meus pais, por conta de todo o apoio que me dão a todo momento.</br>
INSERT INTO movies ( `name`, category) VALUES ('Francisca' ,'BEST MOM IN THE WORLD');</br>
INSERT INTO movies ( `name`, category) VALUES ('Antonio', 'BEST DAD IN THE WORLD');
