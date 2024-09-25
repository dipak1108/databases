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













