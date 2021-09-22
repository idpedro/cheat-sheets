# Criando banco  de dados com relacionamento simples



```sql
# Cria o banco de dados
CREATE DATABASE escola;
# selecionar o banco de dados;
use escola;
# Criando a tabela de usuarios
## criando o modelo do meu usuarios 
CREATE TABLE alunos 
(	
	id int AUTO_INCREMENT PRIMARY KEY ,
	nome varchar(255),
  criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
 	atualizado_em TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
# Mostra estrutura do banco de dados
show tables from escola;
desc escola;
#  Inserindo primeiro aluno
INSERT INTO alunos (nome) VALUES ("Juininho");
INSERT INTO alunos (nome) VALUES ("Carlos");
INSERT INTO alunos (nome) VALUES ("Luquinhas");
## consultando tabela
select * from alunos;
## Atualizando dados na tabela
update alunos set nome="Carlinhos" where id=4;
update alunos set nome="Lucas" where nome="Luquinhas";
## Deletando todos os dados da tabela 
## Não faça isso 
delete from alunos;
## deletando dados de forma correta  
delete from alunos where id=4;
## Alterando coluna da nossa tabela
ALTER TABLE alunos MODIFY nome varchar(150) not null unique; 
## o comando a seguir da erro pois já existe um lucas na nossa amada tabelinha :)
INSERT INTO alunos (nome) VALUES ("Lucas");
create table notas (
  	id_aluno int ,
	pontuacao int not null,
  	prova varchar(150),
  	FOREIGN KEY (id_aluno) REFERENCES alunos(id)
);
# Inserindo dados na tabela de notas para o aluno carlos
insert into notas (id_aluno,pontuacao,prova) values (3,0,"Matematica")
# Juntando dados das tabelas
SELECT
	alunos.nome,notas.pontuacao,notas.prova
FROM 
	alunos
JOIN notas ON notas.id_aluno = alunos.id where notas.pontuacao > 4 ;
```

