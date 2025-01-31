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

# Dicionário de Dados


## Entidade Aluno
| Entidade | Atributo       | Tipo de Dados| Comprimento | Restrições         | Descrição                           |
|----------|----------------|--------------|-------------|--------------------|-------------------------------------|
| Aluno    | RA             | Inteiro      | 6 bytes     | PK, NOT NULL       | Código de identificação do aluno    |
|          | Nome_Aluno     | Caractere    | 20 bytes    | NOT NULL           | Nome do aluno                       |
|          | Sobrenome_Aluno| Caractere    | 50 bytes    | NOT NULL           | Sobrenome do aluno                  |
|          | CPF            | Caractere    | 11 bytes    | NOT NULL, UNIQUE   | CPF do aluno                        |
|          | Status         | Caractere    | 1 byte      | NOT NULL           | Status da matrícula do aluno        |
|          | Nome_Mae       | Caractere    | 80 bytes    | NOT NULL           | Nome da mãe do aluno                |
|          | Nome_Pai       | Caractere    | 80 bytes    | NULL               | Nome do pai do aluno                |
|          | Sexo           | Caractere    | 1 byte      | NOT NULL           | Sexo do aluno                       |
|          | Cod_Turma      | Inteiro      | 4 bytes     | FK, NOT NULL       | Código de identificação da turma    |
|          | Cod_Curso      | Inteiro      | 4 bytes     | FK, NOT NULL       | Código de identificação do curso    |
|          | E-mail         | Caractere    | 60 bytes    | NOT NULL           | E-mail do aluno                     |
|          | Whatsapp       | Caractere    | 11 bytes    | NULL               | Whatsapp do aluno                   |
