# Modelo Conceitual e Lógico da Mecanica, Desenvolvido pelo Bootcamp da DIO

## Descricao Modelo Conceitual da Mecânica

<p align="center">
  <img src="Modelo_Conceitual.png" width="550" title="Modelo Conceitual">
  
</p>

##

## Descricao Modelo Lógico da Mecânica

<p align="center">
  <img src="Modelo_logico.png" width="750" title="Modelo Lógico">
  
</p>

##

## Código SQL

````bash
$ CREATE TABLE Cliente 
( 
 nome VARCHAR(n),  
 cpf VARCHAR(n),  
 contato VARCHAR(n),  
 idCliente INT PRIMARY KEY,  
 UNIQUE (cpf)
); 
````

````bash
$ CREATE TABLE Pedido 
( 
 servico VARCHAR(n),  
 descricao VARCHAR(n),  
 idPedido INT PRIMARY KEY,  
 confirmado VARCHAR(n),  
 data DATE,  
 idCliente INT,  
 codEquipe INT,  
); 
````
````bash
$ CREATE TABLE Pedido 
( 
 servico VARCHAR(n),  
 descricao VARCHAR(n),  
 idPedido INT PRIMARY KEY,  
 confirmado VARCHAR(n),  
 data DATE,  
 idCliente INT,  
 codEquipe INT,  
); 
````

````bash
$ CREATE TABLE Servico 
( 
 descricao VARCHAR(n),  
 idServico INT PRIMARY KEY,  
 nome VARCHAR(n),  
 disponivel VARCHAR(n),  
 valor FLOAT,  
 idOrdem_Servico INT,  
); 

````
````bash
$ CREATE TABLE Peca 
( 
 idPeca INT PRIMARY KEY,  
 descricao VARCHAR(n),  
 nome VARCHAR(n),  
 valor FLOAT,  
 disponivel VARCHAR(n),  
 idOrdem_Servico INT,  
); 

````
````bash
$ CREATE TABLE Ordem_Servico 
( 
 idOrdem INT PRIMARY KEY,  
 valor FLOAT,  
 status VARCHAR(n),  
 data_de_conclusao DATE,  
 data_de_emissao DATE,  
 idPedido INT,  
); 
````
````bash
CREATE TABLE Equipe 
( 
 nome VARCHAR(n),  
 endereco VARCHAR(n),  
 especialidade VARCHAR(n),  
 codEquipe INT PRIMARY KEY,  
); 
````
````bash
ALTER TABLE Pedido ADD FOREIGN KEY(idCliente) REFERENCES Cliente (idCliente)
ALTER TABLE Pedido ADD FOREIGN KEY(codEquipe) REFERENCES Equipe (codEquipe)
ALTER TABLE Servico ADD FOREIGN KEY(idOrdem_Servico) REFERENCES Ordem_Servico (idOrdem_Servico)
ALTER TABLE Peca ADD FOREIGN KEY(idOrdem_Servico) REFERENCES Ordem_Servico (idOrdem_Servico)
ALTER TABLE Ordem_Servico ADD FOREIGN KEY(idPedido) REFERENCES Pedido (idPedido)

````
