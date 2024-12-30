# Banco db_Faculdade

Respositório para criação da base de dados db_Faculdade, meu primeiro projeto na área de dados.

Adicionei mais uma linha do arquivo README.md dessa vez através do repositório remoto do GitHub.

Projeto Prático Curso SQL Server - Bóson Treinamentos
Banco de Dados para Gerenciamento de uma Faculdade.

Objetivo do Banco de Dados:

Realizar controle centralizado de alunos, professores, cursos, disciplinas, histórico e turmas.

Fases do Projeto

•	Levantamento de Requisitos.
•	Identificação de Entidades e Relacionamentos.
•	Modelo E-R.
•	Diagrama E-R.
•	Dicionário de Dados.
•	Normalização.
•	Testes Básicos.

# Regas de Negócio

•	Um aluno só pode estar matriculado em um curso por vez.
•	Alunos possuem um código de identificação (RA).
•	Cursos são compostos por disciplinas.
•	Cada disciplina terá no máximo 30 alunos por turma.
•	As disciplinas podem ser obrigatórias ou optativas, dependendo do curso.
•	As disciplinas pertencem, a departamentos específicos.
•	Cada disciplinas possui um código de identificação.
•	Alunos podem trancar matrícula, não estando então matriculados em nenhuma disciplina no semestre.
•	Em cada semestre, cada aluno pode se matricular em no máximo 9 disciplinas.
•	O aluno só pode ser reprovado no máximo 3 vezes na mesma disciplina.
•	A faculdade terá no máximo 3.000 alunos matriculados simultaneamente, em 10 cursos distintos.
•	Entram 300 alunos novos por ano.
•	Existem 90 disciplinas no total disponíveis.
•	Um histórico traz todas as disciplinas cursadas por um aluno, incluindo nota final, frequência e período do curso realizado.
•	Professores podem ser cadastrados mesmo sem lecionar disciplinas.
•	Existem 40 professores trabalhando na faculdade.
•	Cada professor irá lecionar no máximo 4 disciplinas diferentes.
•	Cada professor é vinculado a um departamento.
•	Professores são identificados por um código de professor.
