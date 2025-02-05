# Banco de Dados - db_Faculdade

### Objetivo do Banco de Dados

Este banco de dados foi desenvolvido durante o curso de SQL Server promovido pelo professor **Fábio dos Reis** da **Bóson Treinamentos** com o propósito de fornecer uma base estruturada para a realização de testes de inserção de dados. Ele permite simular operações de inserção de registros em diferentes tabelas, possibilitando a validação de regras de integridade, desempenho de consultas e otimização de comandos SQL. Essa estrutura auxilia no aprimoramento e ajuste de procedimentos de manipulação de dados antes da aplicação em ambientes produtivos.

# Fases do Projeto 

* Levantamento de Requisitos.
* Identificação de Entidades e Relacionamentos.
* Modelo E-R.
* Diagrama E-R.
* Dicionário de Dados.
* Normalização na 1ª, 2ª e 3ª formas normais.
* Implementação do banco ‘db_Faculdade’.
* Testes Básicos.

# Regras de Negócio

* Um aluno só pode estar matriculado em um curso por vez.
* Alunos possuem um código de identificação (RA).
* Cursos são compostos por disciplinas.
* Cada disciplina terá no máximo 30 alunos por turma.
* As disciplinas podem ser obrigatórias ou optativas, dependendo do curso.
* As disciplinas pertencem, a departamentos específicos.
* Cada disciplinas possui um código de identificação.
* Alunos podem trancar matrícula, não estando então matriculados em nenhuma disciplina no semestre.
* Em cada semestre, cada aluno pode se matricular em no máximo 9 disciplinas.
* O aluno só pode ser reprovado no máximo 3 vezes na mesma disciplina.
* A faculdade terá no máximo 3.000 alunos matriculados simultaneamente, em 10 cursos distintos.
* Entram 300 alunos novos por ano.
* Existem 90 disciplinas no total disponíveis.
* Um histórico traz as disciplinas cursadas por um aluno, incluindo nota final, frequência e período do curso.
* Professores podem ser cadastrados mesmo sem lecionar disciplinas.
* Existem 40 professores trabalhando na faculdade.
* Cada professor irá lecionar no máximo 4 disciplinas diferentes.
* Cada professor é vinculado a um departamento.
* Professores são identificados por um código de professor.

#

# Geração de Dados Fictícios para Testes

Para validar a estrutura e o funcionamento do banco de dados, utilizei dados fictícios cedidos durante o curso de SQL Server da Bóson Treinamentos e dados fictícios gerados por IA generativa, onde os dados foram gerados utilizando **ChatGPT** para os nomes dos alunos, nomes dos professores, e-mail, cpf, nome da mãe, nome do pai, endereços, whatsapp, números de telefone etc. O objetivo era simular um ambiente realista, garantindo que as tabelas e os relacionamentos fossem testados corretamente. Os dados passaram por verificações para evitar erros manter a integridade e coerência esperadas dentro do contexto acadêmico.

Confira um exemplo de dados gerados através de IA generativa e o resultado de uma consulta a base de dados:

```sql
-- Inserindo dados na tabela Aluno
INSERT INTO Aluno (Nome_Aluno, Sobrenome_Aluno, Status, CPF, Sexo, Nome_Mae, Nome_Pai, Email, Whatsapp, Cod_Turma, Cod_Curso)
VALUES
    ('Ronaldo', 'Nazário', '1', '14578914538', 'M', 'Sônia Nazário', 'Nélio Nazário', 'ronaldo.nazario@gmail.com', '981234568', 1, 2),
    ('Rivaldo', 'Ferreira', '1', '14670954539', 'M', 'Marinalva Ferreira', 'Romildo Ferreira', 'rivaldo.ferreira@yahoo.com', '971741249', 2, 4),
    ('Ronaldinho', 'Gaúcho', '1', '14709845340', 'M', 'Dona Miguelina', 'Seu João', 'ronaldinho.gaucho@hotmail.com', '985781413', 3, 5),
    ('Cafu', 'Marques', '1', '14823651541', 'M', 'Maria Marques', 'Toninho Marques', 'cafu.marques@gmail.com', '965637858', 2, 6),
    ('Roberto', 'Carlos', '1', '14968914542', 'M', 'Dona Vera', 'Antônio Carlos', 'roberto.carlos@hotmail.com', '974267424', 1, 3),
    ('Zinédine', 'Zidane', '1', '15088914543', 'M', 'Malika Zidane', 'Smail Zidane', 'zidane.fernandes@outlook.com', '932619561', 3, 1),
    ('Thierry', 'Henry', '1', '15178914544', 'M', 'Maryse Thierry', 'Antoine Thierry', 'henry.thierry@gmail.com', '951234569', 2, 5),
    ('David', 'Beckham', '1', '15270954545', 'M', 'Sandra Beckham', 'Ted Beckham', 'beckham.david@yahoo.com', '961741250', 1, 4),
    ('Francesco', 'Totti', '1', '15309845346', 'M', 'Fiorella Totti', 'Enzo Totti', 'totti.francesco@hotmail.com', '975781414', 3, 2),
    ('Andriy', 'Shevchenko', '1', '15423651547', 'M', 'Lyubov Shevchenko', 'Mykola Shevchenko', 'shevchenko.andriy@gmail.com', '955637859', 2, 6),
    ('Alessandro', 'Del Piero', '1', '15568914548', 'M', 'Bruna Del Piero', 'Gino Del Piero', 'delpiero.alessandro@hotmail.com', '984267425', 1, 3),
    ('Raúl', 'González', '1', '15688914549', 'M', 'María González', 'Pedro González', 'raul.gonzalez@outlook.com', '942619562', 3, 5),
    ('Luís', 'Figo', '1', '15778914550', 'M', 'Dona Antónia', 'Manuel Figo', 'figo.luis@gmail.com', '971234570', 2, 1),
    ('Ricardo', 'Izecson', '1', '15870954551', 'M', 'Simone dos Santos', 'Bosco Leite', 'kaka.ricardo@yahoo.com', '981741251', 1, 4);

```

![Tabela Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Funcionamento%20db_Faculdade/select_08.png)

#

# Ferramentas e Tecnologias Utilizadas

* **SGBD:** SQL Server - Utilizado para criar e gerenciar o banco de dados, além de executar consultas SQL para manipulação e análise dos dados.
* **Linguagem de Consulta:** SQL - linguagem de consulta usada para gerenciar e manipular bancos de dados relacionais, ela é especializada na interação com o banco de dados.
* **Modelagem:** BRModelo - Utilizado para modelagem do banco de dados e criação de diagramas de entidade-relacionamento (ER).
* **Dicionário de Dados:** Excel - Software usado para criação do dicionário de dados.
* **Readme:** Visual Studio Code - Utilizado para edição do arquivo Readme.

# Modelagem

Nesta seção, apresentamos a modelagem dos diagramas Entidade-Relacionamento (ER) do banco de dados, começando pelo modelo conceitual e avançando para o modelo lógico. O modelo conceitual foca na estrutura geral do banco, destacando entidades e seus relacionamentos, enquanto o modelo lógico detalha os atributos, chaves primárias e estrangeiras, refinando a modelagem para a implementação do banco de dados.

#

## Diagramas Entidade Relacionamento (ER)

### Modelo Conceitual
O diagrama conceitual representa uma visão de alto nível da estrutura do banco de dados, destacando as principais entidades e seus relacionamentos, sem detalhar atributos específicos. Este modelo serve para mapear os principais conceitos e suas conexões, facilitando o entendimento da estrutura do banco antes da implementação técnica.

O banco de dados foi modelado para armazenar e gerenciar informações acadêmicas de uma faculdade, abrangendo o cadastro de alunos, professores, cursos, disciplinas, turmas, departamentos e histórico escolar. Entre as principais entidades, destacam-se:

* **Aluno:** Representa os estudantes matriculados na instituição. Cada aluno pode estar vinculado a uma turma e a um curso.

* **Curso:** Contém os cursos oferecidos pela faculdade, sendo associados a um departamento específico.

* **Professor:** Representa os docentes da instituição, que pertencem a um departamento e lecionam disciplinas.

* **Disciplina:** Representa as matérias lecionadas nos cursos, podendo ter pré-requisitos e estar vinculadas a um departamento.

* **Departamento:** Administração acadêmica responsável pelos cursos e disciplinas.

![Modelo Conceitual](https://github.com/rosbergalves/db_Faculdade/blob/main/Diagrama%20ER/DiagramaER_ModeloConceitual.png)

#

### Modelo Lógico
O diagrama lógico refina o modelo conceitual, detalhando a estrutura do banco de dados com a inclusão de atributos, chaves primárias, chaves estrangeiras e tabelas associativas para normalizar os relacionamentos.

A modelagem lógica seguiu as melhores práticas de banco de dados, garantindo:

* Integridade referencial, com a definição de chaves estrangeiras conectando tabelas inter-relacionadas.

* Eliminação de redundâncias, aplicando a normalização até a Terceira Forma Normal (3FN) para garantir a eficiência no armazenamento e minimizar inconsistências.

* Relacionamentos N:N (Muitos para Muitos) representados por tabelas associativas, como:

    * **Aluno_Disciplina:** Relaciona os alunos às disciplinas cursadas.
    * **Professor_Disciplina:** Relaciona os professores às disciplinas que lecionam.
    * **Curso_Disciplina:** Mapeia as disciplinas pertencentes a cada curso.
    * **Disciplina_Historico:** Associa as disciplinas ao histórico dos alunos.

![Modelo Lógico](https://github.com/rosbergalves/db_Faculdade/blob/main/Diagrama%20ER/DiagramaER_ModeloL%C3%B3gico.png)

#

Para garantir a integridade referencial e eficiência da modelagem, o banco de dados foi projetado seguindo os princípios das 1ª, 2ª e 3ª formas normais:

* **Primeira Forma Normal (1FN):** Cada tabela contém apenas valores atômicos, sem grupos repetitivos ou colunas multivaloradas, garantindo que todos os atributos sejam indivisíveis.

* **Segunda Forma Normal (2FN):** Todas as tabelas atendem à 1FN e não possuem dependências parciais, ou seja, todos os atributos não-chave dependem totalmente da chave primária.

* **Terceira Forma Normal (3FN):** Além de atender à 2FN, eliminamos dependências transitivas, garantindo que os atributos não-chave dependam apenas da chave primária e não de outros atributos não-chave.

Essas normalizações contribuem para a eliminação de redundâncias e a melhoria do desempenho do banco, garantindo maior confiabilidade nos testes e inserções de dados. Dessa forma, este banco de dados será capaz de gerenciar informações acadêmicas de alunos, professores, cursos, disciplinas, departamentos históricos, turmas, endereços etc.


# Dicionário de Dados

<span style="font-size: 12px;">[Download do dicionário de dados completo](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Dicion%C3%A1rio%20de%20Dados%20db_Faculdade.xlsx)</span>

## Entidades

### Entidade Aluno

![Entidade Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_aluno.png)

### Entidade Curso

![Entidade Curso](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_curso.png)

### Entidade Turma

![Entidade Turma](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_turma.png)

### Entidade Disciplina

![Entidade Disciplina](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_disciplina.png)

### Entidade Professor

![Entidade Professor](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_professor.png)

### Entidade Departamento

![Entidade Departamento](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_departamento.png)

### Entidade Histórico

![Entidade Historico](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_hist%C3%B3rico.png)

### Entidade Aluno_Disciplina

![Entidade Aluno_Disciplina](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_aluno_disciplina.png)

### Entidade Professor_Disciplina

![Entidade Professor_Discipl](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_professor_disciplina.png)

### Entidade Curso_Disciplina

![Entidade Curso_Discipli](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_curso_disciplina.png)

### Entidade Disciplina_Historico

![Disciplina_Historico](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_disciplina_hist%C3%B3rico.png)

### Entidade Endereço_Aluno

![Entidade Endereço_Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_endere%C3%A7o_aluno.png)

### Entidade Cidade

![Entidade Cidade](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_cidade.png)

### Entidade UF

![Entidade UF](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_uf.png)

### Entidade Tipo_Logradouro

![Entidade Tipo_Logradouro](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_tipo_logradouro.png)

### Entidade Telefone_Aluno

![Entidade Telefone_Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_telefone_aluno.png)

### Entidade Tipo_Telefone

![Entidade Tipo_Telefone](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Entidades/entidate_tbl_tipo_telefone.png)

#

## Atributos

### Atributos Entidade Aluno

![Atributos Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_aluno.png)

### Atributos Entidade Curso

![Atributos Curso](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_curso.png)

### Atributos Entidade Turma

![Atributos Turma](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_turma.png)

### Atributos Entidade Disciplina

![Atributos Disciplina](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_disciplina.png)

### Atributos Entidade Professor

![Atributos Professor](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_professor.png)

### Atributos Entidade Departamento

![Atributos Departamento](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_departamento.png)

### Atributos Entidade Histórico

![Atributos Histórico](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_hist%C3%B3rico.png)

### Atributos Entidade Aluno_Disciplina

![Atributos Aluno_Disciplina](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_aluno_disciplina.png)

### Atributos Entidade Professor_Disciplina

![Atributos Professor_Disciplina](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_professor_disciplina.png)

### Atributos Entidade Curso_Disciplina

![Atributos Curso_Disciplina](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_curso_disciplina.png)

### Atributos Entidade Disciplina_Histórico

![Atributos Disciplina_Histórico](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_disciplina_hist%C3%B3rico.png)

### Atributos Entidade Endereco_Aluno

![Atributos Endereco_Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_endere%C3%A7o_aluno.png)

### Atributos Entidade Cidade

![Atributos Cidade](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_cidade.png)

### Atributos Entidade UF

![Atributos UF](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_uf.png)

### Atributos Entidade Tipo_Logradouro

![Atributos Tipo_Logradouro](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_tipo_logradouro.png)

### Atributos Entidade Telefone_Aluno

![Atributos Telefone_Aluno](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_telefone_aluno.png)

### Atributos Entidade Tipo_Telefone

![Atributos Tipo_Telefone](https://github.com/rosbergalves/db_Faculdade/blob/main/Dicion%C3%A1rio%20de%20Dados/Atributos/atributos_tbl_tipo_telefone.png)

#

# Script de Criação do Banco de Dados

```sql
--Criando o Banco
CREATE DATABASE db_Faculdade;

--Conectando ao Banco
USE db_Faculdade;

--Tabela para cadastro de unidades federativas
CREATE TABLE UF (
	Cod_UF INT PRIMARY KEY IDENTITY,
	Nome_Estado VARCHAR(50) NOT NULL,
	Sigla CHAR(2) NOT NULL
);

--Tabela para cadastro de cidades
CREATE TABLE Cidade (
	Cod_Cidade INT PRIMARY KEY IDENTITY,
	Nome_Cidade VARCHAR(100),
	Cod_UF INT NOT NULL,
	CONSTRAINT fk_uf_cidade FOREIGN KEY (Cod_UF) REFERENCES UF (Cod_UF)
);

--Tabela para cadastro dos departamentos da faculdade
CREATE TABLE Departamento (
	Cod_Departamento INT PRIMARY KEY IDENTITY,
	Nome_Departamento VARCHAR(100) NOT NULL
);

--Tabela para cadastro dos professores da faculdade
CREATE TABLE Professor (
	Cod_Professor INT PRIMARY KEY IDENTITY,
	Nome_professor VARCHAR(20) NOT NULL,
	Sobrenome_Professor VARCHAR(50) NOT NULL,
	Status_Professor BIT NOT NULL,
	Cod_Departamento INT NOT NULL,
	CONSTRAINT fk_departamento_professor FOREIGN KEY (Cod_Departamento) REFERENCES Departamento (Cod_Departamento)
);

--Tabela para cadastro dos cursos oferecidos pela faculdade
CREATE TABLE Curso (
	Cod_Curso INT PRIMARY KEY IDENTITY,
	Nome_Curso VARCHAR(40),
	Cod_Departamento INT NOT NULL,
	CONSTRAINT fk_departamento_curso FOREIGN KEY (Cod_Departamento) REFERENCES Departamento (Cod_Departamento)
);

--Tabela para cadastro das turmas da faculdade
CREATE TABLE Turma (
	Cod_Turma INT PRIMARY KEY IDENTITY,
	Periodo VARCHAR(5) NOT NULL,
	Qtde_Alunos INT NOT NULL,
	Data_Inicio DATE NOT NULL,
	Data_Fim DATE NOT NULL,
	Cod_Curso INT NOT NULL,
	CONSTRAINT fk_curso_turma FOREIGN KEY (Cod_Curso) REFERENCES Curso (Cod_Curso)
);

--Tabela para cadastro das disciplinas cursadas na faculdade
CREATE TABLE Disciplina (
	Cod_Disciplina INT PRIMARY KEY IDENTITY,
	Nome_Disciplina VARCHAR(30) NOT NULL,
	Descricao VARCHAR(200),
	Qtde_Alunos INT NOT NULL,
	Carga_Horaria INT NOT NULL,
	Cod_Disciplina_Depende INT NULL,
	Cod_Departamento INT NOT NULL,
	CONSTRAINT fk_departamento_disciplina FOREIGN KEY (Cod_Departamento) REFERENCES Departamento (Cod_Departamento),
	CONSTRAINT fk_disciplinadepende_disciplina FOREIGN KEY (Cod_Disciplina_Depende) REFERENCES Disciplina (Cod_Disciplina)
);

--Tabela aasociativa entre as tabelas Professor e Disciplina 
CREATE TABLE Professor_Disciplina (
	Cod_Professor INT NOT NULL,
	Cod_Disciplina INT NOT NULL,
	PRIMARY KEY (Cod_Professor, Cod_Disciplina),
	CONSTRAINT fk_professor_professordisciplina FOREIGN KEY (Cod_Professor) REFERENCES Professor (Cod_Professor),
	CONSTRAINT fk_disciplina_professordisciplina FOREIGN KEY (Cod_Disciplina) REFERENCES Disciplina (Cod_Disciplina)
);

--Tabela associativa entre as tabelas Curso e Disciplina
CREATE TABLE Curso_Disciplina (
	Cod_Curso INT NOT NULL,
	Cod_Disciplina INT NOT NULL,
	PRIMARY KEY (Cod_Curso, Cod_Disciplina),
	CONSTRAINT fk_curso_cursodisciplina FOREIGN KEY (Cod_Curso) REFERENCES Curso (Cod_Curso),
	CONSTRAINT fk_disciplina_cursodisciplina FOREIGN KEY (Cod_Disciplina) REFERENCES Disciplina (Cod_Disciplina)
);

--Tabela para cadastro dos alunos da faculdade
CREATE TABLE Aluno (
	RA INT PRIMARY KEY IDENTITY,
	Nome_Aluno VARCHAR(20) NOT NULL,
	Sobrenome_Aluno VARCHAR(50) NOT NULL,
	Status VARCHAR(1) NOT NULL,
	CPF VARCHAR(11) NOT NULL UNIQUE,
	Sexo CHAR(1) NOT NULL,
	Nome_Mae VARCHAR(80) NOT NULL,
	Nome_Pai VARCHAR(80) NULL,
	Email VARCHAR(60) NOT NULL,
	Whatsapp VARCHAR(11) NULL,
	Cod_Turma INT NOT NULL,
	Cod_Curso INT NOT NULL,
	CONSTRAINT fk_turma_aluno FOREIGN KEY (Cod_Turma) REFERENCES Turma (Cod_Turma),
	CONSTRAINT fk_curso_aluno FOREIGN KEY (Cod_Curso) REFERENCES Curso (Cod_Curso)
);

--Tabela associativa entre as tabelas Aluno e Disciplina
CREATE TABLE Aluno_Disciplina (
	RA INT NOT NULL,
	Cod_Disciplina INT NOT NULL,
	PRIMARY KEY (RA, Cod_Disciplina),
	CONSTRAINT fk_aluno_alunodisciplina FOREIGN KEY (RA) REFERENCES Aluno (RA),
	CONSTRAINT fk_disciplina_alunodisciplina FOREIGN KEY (Cod_Disciplina) REFERENCES Disciplina (Cod_Disciplina)
);

--Tabela para cadastro do histórico dos alunos da faculdade
CREATE TABLE Historico (
	Cod_Historico INT PRIMARY KEY IDENTITY,
	Data_Inicio DATE NOT NULL,
	Data_Fim DATE NULL,
	RA INT NOT NULL,
	CONSTRAINT fk_aluno_historico FOREIGN KEY (RA) REFERENCES Aluno (RA)
);

--Tabela associativa entre as tabelas Disciplina e Histórico
CREATE TABLE Disciplina_Historico (
	Cod_Historico INT NOT NULL,
	Cod_Disciplina INT NOT NULL,
	Nota DECIMAL NOT NULL,
	Frequencia INT NOT NULL,
	PRIMARY KEY (Cod_Historico, Cod_Disciplina),
	CONSTRAINT fk_historico_disciplinahistorico FOREIGN KEY (Cod_Historico) REFERENCES Historico (Cod_Historico),
	CONSTRAINT fk_disciplina_disciplinahistorico FOREIGN KEY (Cod_Disciplina) REFERENCES Disciplina (Cod_Disciplina)
);

--Tabela para cadstro do tipo de telefone dos alunos da faculdade
CREATE TABLE Tipo_Telefone (
	Cod_Tipo_Telefone INT PRIMARY KEY IDENTITY,
	Tipo_Telefone VARCHAR(8) NOT NULL
);

--Tabela para cadastro dos números de telefone dos alunos da faculdade
CREATE TABLE Telefone_Aluno (
	Cod_Telefone_Aluno INT PRIMARY KEY IDENTITY,
	Num_Telefone VARCHAR(20) NOT NULL,
	RA INT NOT NULL,
	Cod_Tipo_Telefone INT NOT NULL,
	CONSTRAINT fk_aluno_telefonealuno FOREIGN KEY (RA) REFERENCES Aluno (RA),
	CONSTRAINT fk_tipotelefone_telefonealuno FOREIGN KEY (Cod_Tipo_Telefone) REFERENCES Tipo_Telefone (Cod_Tipo_Telefone)
);

--Tabela para cadastro do tipo de logradouro do endereço dos alunos da faculdade
CREATE TABLE Tipo_Logradouro (
	Cod_Tipo_Logradouro INT PRIMARY KEY IDENTITY,
	Tipo_Logradouro VARCHAR(11) NOT NULL
);

--Tabela para cadastro dos endereços dos alunos da faculdade
CREATE TABLE Endereco_Aluno (
	Cod_Endereco_Aluno INT PRIMARY KEY IDENTITY,
	Nome_Rua VARCHAR(50) NOT NULL,
	Numero INT NOT NULL,
	Complemento VARCHAR(20) NULL,
	CEP INT NOT NULL,
	Cod_Tipo_Logradouro INT NOT NULL,
	RA INT NOT NULL,
	Cod_Cidade INT NULL,
	Id_UF INT NULL,
	CONSTRAINT fk_aluno_enderecoaluno FOREIGN KEY (RA) REFERENCES Aluno (RA),
	CONSTRAINT fk_tipologradouro_enderecoaluno FOREIGN KEY (Cod_Tipo_Logradouro) REFERENCES Tipo_Logradouro (Cod_Tipo_Logradouro),
	CONSTRAINT fk_Cod_Cidade FOREIGN KEY (Cod_Cidade) REFERENCES Cidade (Cod_Cidade),
	CONSTRAINT fk_Cod_UF FOREIGN KEY (Cod_UF) REFERENCES UF (Cod_UF)
);
```

# Demonstração do Funcionamento do Banco de Dados

Aqui podemos acompanhar o funcionamento do banco de dados através de consultas SQL e seus respectivos resultados. As capturas de tela ilustram a interação com o banco, demonstrando a integridade dos dados e a eficácia das relações estabelecidas entre as tabelas.

Para validar o modelo de dados, foram realizadas consultas que demonstram:

* A integridade das relações entre as tabelas.
* O correto armazenamento e recuperação das informações.
* A extração de dados relevantes para fins acadêmicos e administrativos como pode ser observado nas imagens abaixo.

![](https://github.com/rosbergalves/db_Faculdade/blob/main/Funcionamento%20db_Faculdade/select_01.png)
✅**Resultado da Consulta:** Essa consulta confirma que os alunos estão corretamente vinculados aos cursos e às turmas, as relações entre as tabelas Aluno, Curso e Turma estão funcionando corretamente e os alunos possuem informações de curso e período corretamente associadas.
#

![](https://github.com/rosbergalves/db_Faculdade/blob/main/Funcionamento%20db_Faculdade/select_02.png)
✅**Resultado da Consulta:** Essa consulta retorna que o aluno com RA = 3 tem registros de disciplinas cursadas e notas associadas, a integridade referencial entre os históricos e as disciplinas está correta e O relacionamento entre Aluno_Disciplina e Disciplina_Historico está bem definido.
#

![](https://github.com/rosbergalves/db_Faculdade/blob/main/Funcionamento%20db_Faculdade/select_03.png)
✅**Resultado da Consulta:** A consulta realiza uma junção (INNER JOIN) entre três tabelas: Professor, Professor_Disciplina e Disciplina, o que confirma que o relacionamento entre essas tabelas está corretamente implementado, associando os professores às disciplinas que lecionam.
#

![](https://github.com/rosbergalves/db_Faculdade/blob/main/Funcionamento%20db_Faculdade/select_04.png)
✅**Resultado da Consulta:** A consulta confirma a integração entre múltiplas tabelas, Aluno, Telefone_Aluno, Tipo_Telefone, Endereco_Aluno e Tipo_Logradouro.