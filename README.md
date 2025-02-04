# Banco de Dados - db_Faculdade

### Objetivo do Banco de Dados

Este banco de dados foi desenvolvido com o propósito de fornecer uma base estruturada para a realização de testes de inserção de dados. Ele permite simular operações de inserção de registros em diferentes tabelas, possibilitando a validação de regras de integridade, desempenho de consultas e otimização de comandos SQL. Essa estrutura auxilia no aprimoramento e ajuste de procedimentos de manipulação de dados antes da aplicação em ambientes produtivos.

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
* Um histórico traz todas as disciplinas cursadas por um aluno, incluindo nota final, frequência e período do curso realizado.
* Professores podem ser cadastrados mesmo sem lecionar disciplinas.
* Existem 40 professores trabalhando na faculdade.
* Cada professor irá lecionar no máximo 4 disciplinas diferentes.
* Cada professor é vinculado a um departamento.
* Professores são identificados por um código de professor.

# Modelagem

Nesta seção, apresentamos a modelagem dos diagramas Entidade-Relacionamento (ER) do banco de dados, começando pelo modelo conceitual e avançando para o modelo lógico. O modelo conceitual foca na estrutura geral do banco, destacando entidades e seus relacionamentos, enquanto o modelo lógico detalha os atributos, chaves primárias e estrangeiras, refinando a modelagem para a implementação do banco de dados.

## Diagramas Entidade Relacionamento (ER)

### Diagrama Conceitual
O diagrama conceitual representa uma visão de alto nível da estrutura do banco de dados, destacando as principais entidades e seus relacionamentos, sem detalhar atributos específicos. Este modelo serve para mapear os principais conceitos e suas conexões, facilitando o entendimento da estrutura do banco antes da implementação técnica.

O banco de dados foi modelado para armazenar e gerenciar informações acadêmicas de uma faculdade, abrangendo o cadastro de alunos, professores, cursos, disciplinas, turmas, departamentos e histórico escolar. Entre as principais entidades, destacam-se:

* **Aluno:** Representa os estudantes matriculados na instituição. Cada aluno pode estar vinculado a uma turma e a um curso.

* **Curso:** Contém os cursos oferecidos pela faculdade, sendo associados a um departamento específico.

* **Professor:** Representa os docentes da instituição, que pertencem a um departamento e lecionam disciplinas.

* **Disciplina:** Representa as matérias lecionadas nos cursos, podendo ter pré-requisitos e estar vinculadas a um departamento.

* **Departamento:** Administração acadêmica responsável pelos cursos e disciplinas.

![Modelo Conceitual](https://github.com/rosbergalves/db_Faculdade/blob/main/Diagrama%20ER/DiagramaER_ModeloConceitual.png)

#

### Diagrama Lógico
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

### Entidade Historico

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

# Script de Criação do Banco db_Faculdade


´´´sql
--Tabela para cadastro de unidades federativas
CREATE TABLE UF (
	Cod_UF INT PRIMARY KEY IDENTITY,
	Nome_Estado VARCHAR(50) NOT NULL,
	Sigla CHAR(2) NOT NULL
);
´´´
