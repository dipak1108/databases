# Week [3]

### Exe 2.1
select * from goal;
![ex1 png](https://github.com/user-attachments/assets/e50d5bc8-2fd6-4c1f-bdb9-e1fab3de9f18)

### Exe 2.2
select name from airport where iso_country = "FI";
![ex2 md](https://github.com/user-attachments/assets/0cf12ce7-bed5-4afa-ab5d-8c58e52eddb9)

###  Exe 2.3
select name from airport where iso_country = "FI" order by name;
![ex3 md](https://github.com/user-attachments/assets/b5978ea5-a61b-4173-8db5-cb4f804d85c9)

###  Exe 2.4
select name, type from airport where iso_country = "FI" order by type, name;
![ex4 md](https://github.com/user-attachments/assets/310dfdae-c28a-469e-9c8d-5f1749b5cb7c)

###  Exe 2.5
select name from country where name like "F%";
![ex5 md](https://github.com/user-attachments/assets/bd9ccac1-7160-4ae5-aabe-0d7a3ca225a9)

###  Exe 2.6
select name from country where name like "%F%";
![ex6 md](https://github.com/user-attachments/assets/38a9468a-a846-4645-868d-221f3cc2ea3d)

###  Exe 2.7
select location from game where screen_name = "Vesa";
![ex7 md](https://github.com/user-attachments/assets/0c5ea32c-d6e3-43fb-80ae-6b0c71d9bb91)

###  Exe 2.8
select co2_consumed from game where screen_name = "Ilkka";
![ex8 md](https://github.com/user-attachments/assets/e8354434-21ee-4a74-9773-1827324cb3c2)

###  Exe 2.9
select distinct co2_budget from game;
![ex9 md](https://github.com/user-attachments/assets/ca019df4-bfc6-41c6-907e-379c67b0cb0f)

###  Exe 2.10
select screen_name ,co2_budget , co2_consumed,(@c02_left:=co2_budget - co2_consumed) as co2_left from game where screen_name = "Ilkka";
![ex10 md](https://github.com/user-attachments/assets/217cdf49-c41a-432e-8786-76b1c2c311ff)




###  Exe 3.1
select country.name as "country name", airport.name as "airport name"
from airport, country
where airport.iso_country = country.iso_country and country.name = "Iceland";
![ex 1md](https://github.com/user-attachments/assets/0f7510ac-f4e6-4f25-87c4-df689f12d246)

###  Exe 3.2
 select airport.name as "airport name" FROM airport JOIN country ON airport.iso_country = country.iso_country WHERE country.name="France" and airport.type = "large_airport";
 ![ex 2md](https://github.com/user-attachments/assets/409b6d85-f407-4643-9042-6ff1651ee089)

###  Exe 3.3
select country.name as country_name, airport.name as airport_name from airport, country where airport.iso_country = country.iso_country and country.continent = "AN";
![ex 3md](https://github.com/user-attachments/assets/2b151b10-da5f-4e44-b33c-89891be1a395)

###  Exe 3.4
select elevation_ft from airport where name= "Helsinki Vantaa Airport" ;
![ex4 md](https://github.com/user-attachments/assets/2b0d2354-c66b-41dc-8064-a689d715a250)

###  Exe 3.5
select (elevation_ft*0.3048) AS elevation_m from airport where name= "Helsinki Vantaa Airport" ;
![ex5 md](https://github.com/user-attachments/assets/5a666153-8015-4257-821b-11659e2fe180)

###  Exe 3.6
select name from airport where ident="EGKK";
![ex6 md](https://github.com/user-attachments/assets/34be673a-b856-43b5-acf0-636a7097957c)

###  Exe 3.7
select country.name from airport join country on country.iso_country=airport.iso_country where ident="EGKK";
![ex7 md](https://github.com/user-attachments/assets/c7b99150-eb3a-4b76-b031-b3c939bc8be0)

###  Exe 3.8
select name from goal, goal_reached, game where game.id = game_id and goal.id = goal_id and screen_name = "Heini";
![ex8 md](https://github.com/user-attachments/assets/71bdbaeb-1fe5-4c43-8d86-df08f691e3a7)

###  Exe 3.9
select airport.name from airport, goal where goal.name = "clouds" and airport.ident= "EGKK";
![ex9 md](https://github.com/user-attachments/assets/a96b9840-9eae-4b68-a0ed-970c465c54e5)

###  Exe 3.10
select country.name
from country, airport, game, goal, goal_reached
where airport.iso_country = country.iso_country and ident = location and game.id = game_id and goal.id = goal_id and screen_name = "Ilkka" and goal.name = "CLOUDS";
![ex10 md](https://github.com/user-attachments/assets/b1993c81-ffa4-473f-b9d7-6932d3c3abdf)




#Week [4]


### Exe 4.1
select country.name as "country name", airport.name as "airport name"
from country inner join airport on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled_service = "yes";
![ex1 md](https://github.com/user-attachments/assets/fccd7546-7940-4bca-b2ce-b126db97ca33)

### Exe 4.2
select game.screen_name,airport.name
from game  inner join airport on airport.ident=game.location;
![ex2 md](https://github.com/user-attachments/assets/361a2543-2d2d-4e5d-b0ea-7733debb5733)

### Exe 4.3
select screen_name, country.name
from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;
![ex3 md](https://github.com/user-attachments/assets/8198eb79-bb1d-41fb-87ce-d084413c6b29)

### Exe 4.4
select airport.name, screen_name
from airport left join game on ident = location where name like "%Hels%";
![ex4 md](https://github.com/user-attachments/assets/d4915d4b-091f-496f-aeeb-a9c17d1bc6e9)

### Exe 4.5
select goal.name , game.screen_name
from goal
left join goal_reached on goal.id = goal_reached.goal_id
left join game on goal_reached.game_id = game.id;
![ex5 md](https://github.com/user-attachments/assets/a69a32a5-4645-478b-a9c6-c1601d7d5f73)


### Exe 5.1
select country.name 
FROM airport inner 
join country on airport.iso_country=country.iso_country 
where airport.name like "Satsuma%" ;
![ex1 md](https://github.com/user-attachments/assets/c50cb3c3-968c-4f77-8d92-d7f97ef03799)


### Exe 5.2
select name from airport
where iso_country in (
    select iso_country
    from country
    where name = "Monaco"
    );
![ex2 md](https://github.com/user-attachments/assets/c70ca366-0d7a-4407-8090-1d551f315046)

### Exe 5.3
SELECT game.screen_name
from game
where id in (
    select goal_reached.game_id
    from goal_reached
    where goal_reached.goal_id in (
        select id
        from goal
        where name = "CLOUDS"
        )
    );
    ![ex3 md](https://github.com/user-attachments/assets/c1e412ab-13f0-429c-90b2-9de15957be47)

### Exe 5.4
SELECT name
from country
where iso_country not in (
    select iso_country from airport
    );
    ![ex4 md](https://github.com/user-attachments/assets/90d8a277-cf73-48b0-a867-e89320cce36b)

### Exe 5.5
SELECT name
from goal
where id not in (
    select goal_id from goal_reached
    );
![ex5 md](https://github.com/user-attachments/assets/23031e8c-2917-4dc0-b03b-e7fb0b47c1d6)




#Week [5]

### Exe 6.1
select max(elevation_ft) from airport;
![ex1 md](https://github.com/user-attachments/assets/3d4cdb66-be74-4817-94cd-a3303c17be7f)

### Exe 6.2
select continent, count(*) from country group by continent;
![ex2 md](https://github.com/user-attachments/assets/3f09705d-f05f-4040-bc6f-9d098ddeb896)


### Exe 6.3
select screen_name, count(*) from game, goal_reached where id = game_id group by screen_name;
![ex3 md](https://github.com/user-attachments/assets/d128de26-f932-4801-b5d6-ad7fae7752ce)


### Exe 6.4
select screen_name from game where co2_consumed in( select min(co2_consumed) from game );
![ex4 md](https://github.com/user-attachments/assets/94b65730-6849-41e7-bc08-892f9939582d)

### Exe 6.5
select country.name, count(*) from airport, country where airport.iso_country = country.iso_country group by country.iso_country order by count(*) desc limit 50;
![ex5 md](https://github.com/user-attachments/assets/a8fa72e7-d00e-4b1a-aedd-2c96ddcd26a6)


### Exe 6.6
select country.name from airport, country where airport.iso_country = country.iso_country group by country.iso_country having count(*) > 1000;
![ex6 md](https://github.com/user-attachments/assets/626de73c-9759-48e5-b25c-c1c8ad5237db)


### Exe 6.7
select name from airport where elevation_ft in ( select max(elevation_ft) from airport );
![ex7 md](https://github.com/user-attachments/assets/ad3a6405-8531-4afc-a037-410f89746a41)


### Exe 6.8
select name from country where iso_country in ( select iso_country from airport where elevation_ft in( select max(elevation_ft) from airport ) );
![ex8 md](https://github.com/user-attachments/assets/b79754da-eaad-42e2-8123-644f1da67250)

### Exe 6.9
select count(*) from game, goal_reached where id = game_id and screen_name = "Vesa" group by screen_name;
![ex9 md](https://github.com/user-attachments/assets/db862f52-b931-44d3-bd23-7afbba1b01cd)

### Exe 6.10
select name from airport where latitude_deg in( select min(latitude_deg) from airport );
![ex10 md](https://github.com/user-attachments/assets/ba2e11a0-1fc8-441f-8393-843ced0471b5)


### Exe 7.1
update game
set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500
where screen_name = "Vesa";

select * from game;
![ex1)( md](https://github.com/user-attachments/assets/de3916da-71fa-4c4f-8876-97ba532897be)


### Exe 7.2

![ex2 md](https://github.com/user-attachments/assets/8aeda785-d524-48f8-b881-2f790d47d8ce)

  
### Exe 7.3
delete from goal_reached; select * from goal_reached;
![ex3 md](https://github.com/user-attachments/assets/c2be5571-e3d7-4578-925d-b07fa855754c)

### Exe 7.4
delete from game; select * from game;
![ex4 md](https://github.com/user-attachments/assets/eaed95c2-6d83-477b-930c-e3c550721038)




















