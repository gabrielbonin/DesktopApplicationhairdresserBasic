-- MySQL Workbench Forward Engineering

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------

-- -----------------------------------------------------
-- Schema mydb
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `mydb` DEFAULT CHARACTER SET utf8 ;
USE `mydb` ;

-- -----------------------------------------------------
-- Table `mydb`.`agenda`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`agenda` (
  `id_agenda` INT(11) NOT NULL AUTO_INCREMENT,
  `dia_agenda` varchar(12) NOT NULL,
  `hora_agenda` VARCHAR(45) NOT NULL,
  `id_servico` int,
  `id_cliente` int,
  CONSTRAINT fk_ServicAgend FOREIGN KEY (id_servico) REFERENCES servicos (id_servico),
  CONSTRAINT fk_ClientAgend FOREIGN KEY (id_cliente) REFERENCES cliente (id_cliente),
  PRIMARY KEY (`id_agenda`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `mydb`.`cliente`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`cliente` (
  `id_cliente` INT(11) NOT NULL AUTO_INCREMENT,
  `cliente_nome` VARCHAR(45) NOT NULL,
  `cliente_telefone` VARCHAR(45) NOT NULL,
  `cliente_cpf` VARCHAR(45) NOT NULL,
  PRIMARY KEY (`id_cliente`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `mydb`.`produtos`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`produtos` (
  `id_produtos` INT(11) NOT NULL AUTO_INCREMENT,
  `nome_produto` VARCHAR(45) NOT NULL,
  `valor_venda` DOUBLE NOT NULL,
  `quantidade` VARCHAR(45) NOT NULL,
  `valor_compra` DOUBLE NOT NULL,
  PRIMARY KEY (`id_produtos`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `mydb`.`servicos`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`servicos` (
  `id_servico` INT(11) NOT NULL AUTO_INCREMENT,
  `servico` VARCHAR(45) NOT NULL,
  `valor` DOUBLE NOT NULL,
  PRIMARY KEY (`id_servico`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8;


-- -----------------------------------------------------
-- Table `mydb`.`caixa`
-- -----------------------------------------------------
CREATE TABLE IF NOT EXISTS `mydb`.`caixa` (
  `id_caixa` INT NOT NULL AUTO_INCREMENT,
  `caixa_valor` DOUBLE NOT NULL,
  `id_produtos` INT,
  `id_agenda` INT,
  CONSTRAINT fk_ProdCaixa FOREIGN KEY (id_produtos) REFERENCES produtos (id_produtos),
  CONSTRAINT fk_AgendCaixa FOREIGN KEY (id_agenda) REFERENCES clientes (id_agenda),

  PRIMARY KEY (`id_caixa`))
ENGINE = InnoDB;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;


DROP database mydb;
USE MYDB



 
SELECT * FROM servicos
 SELECT * FROM produtos
 SELECT * FROM agenda
 SELECT * FROM cliente
  SELECT agenda.id_agenda, agenda.dia_agenda, agenda.hora_agenda, cliente.cliente_nome, servicos.servico, servicos.valor
 from agenda
 inner join cliente on agenda.id_cliente = cliente.id_cliente
 inner join servicos on agenda.id_servico = servicos.id_servico

 
SELECT id_estoque, quantidade, valor_compra, nome_produto
FROM estoque
left JOIN produtos ON estoque.id_produtos = produtos.id_produtos;



 INSERT INTO servicos (servico, valor) VALUES ('Cabelo', '30');
 INSERT INTO produtos  (nome_produto, valor_venda, quantidade, valor_compra) VALUES ('creme', '23', '2','3');
 INSERT INTO cliente (cliente_nome, cliente_telefone, cliente_cpf) VALUES ('Gabriel Bonin', '19-999999', '4567277171-87');
 INSERT INTO agenda (dia_agenda, hora_agenda, servicos.servico, cliente.nome_cliente) VALUES ('10/01/2020','18:00', '1','1');
 SELECT * FROM cliente;
 
 SELECT estoque.id_estoque, estoque.quantidade, estoque.valor_compra, produtos.nome_produto
FROM estoque
INNER JOIN produtos ON estoque.id_produtos = produtos.id_produtos;
 
 INSERT INTO agenda (dia_agenda, hora_agenda, id_servico, id_cliente) VALUES ('10/01/2020','18:00', '1','1'); 
  INSERT INTO agenda (dia_agenda, hora_agenda, id_servico, id_cliente) VALUES ('14/11/2019','08:00', '2','2'); 
 

 where cliente.cliente_nome = cliente.cliente_nome;
 
 SELECT produtos.nome_produto from produtos
 
 DELETE from agenda
 select * from agenda
 select cliente_nome FROM cliente;
 
 SELECT Id AS Ordem, CONCAT(NomeCliente,'[',IdadeCliente,']') AS 'Cliente[Idade]' FROM ClientesCidades;
 
 SELECT CONCAT( id_cliente,'-', cliente_nome ) as id_nome FROM cliente;
 
 SELECT id_cliente, CONCAT(cliente_nome) as id_nome from cliente

SELECT cliente_nome from cliente
where id_cliente = id_cliente

SELECT id_servico from servicos where servico = servico;
select * from CLIENTE
DELETE  FROM CLIENTE
SELECT id_cliente, CONCAT(id_cliente' - 'cliente_nome)
FROM cliente
 