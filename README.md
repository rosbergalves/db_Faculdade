# Banco de Dados - db_Faculdade

## Objetivo do Banco de Dados
O objetivo é criar um banco de dados para gerenciar informações acadêmicas de alunos, professores, cursos, disciplinas, departamentos históricos, turmas, endereços etc.


# Fases do Projeto 

• Levantamento de Requisitos.

• Identificação de Entidades e Relacionamentos.

• Modelo E-R.

• Diagrama E-R.

• Dicionário de Dados.

• Normalização na 1ª, 2ª e 3ª formas normais.

• Implementação do banco ‘db_Faculdade’.

• Testes Básicos.

# Regras de Negócio

• Um aluno só pode estar matriculado em um curso por vez.

• Alunos possuem um código de identificação (RA).

• Cursos são compostos por disciplinas.

• Cada disciplina terá no máximo 30 alunos por turma.

• As disciplinas podem ser obrigatórias ou optativas, dependendo do curso.

• As disciplinas pertencem, a departamentos específicos.

• Cada disciplinas possui um código de identificação.

• Alunos podem trancar matrícula, não estando então matriculados em nenhuma disciplina no semestre.

• Em cada semestre, cada aluno pode se matricular em no máximo 9 disciplinas.

• O aluno só pode ser reprovado no máximo 3 vezes na mesma disciplina.

• A faculdade terá no máximo 3.000 alunos matriculados simultaneamente, em 10 cursos distintos.

• Entram 300 alunos novos por ano.

• Existem 90 disciplinas no total disponíveis.

• Um histórico traz todas as disciplinas cursadas por um aluno, incluindo nota final, frequência e período do curso realizado.

• Professores podem ser cadastrados mesmo sem lecionar disciplinas.

• Existem 40 professores trabalhando na faculdade.

• Cada professor irá lecionar no máximo 4 disciplinas diferentes.

• Cada professor é vinculado a um departamento.

• Professores são identificados por um código de professor.

# 

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













