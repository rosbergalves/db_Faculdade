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

### Entidades

### Entidade Aluno

| Entidade | Relacionamento   | Nome do Relacionamento | Cardinalidade Miníma | Cardinalidade Máxima | Descrição                                                   |
|----------|------------------|------------------------|----------------------|----------------------|-------------------------------------------------------------|
| Aluno	   | Curso	          | Está matriculado       | 1,1                  | 1,n                  | Tabela para cadastro de informações sobre os alunos.        |
|          | Turma            | Pertence               | 1,1                  | 1,n	                 |                                                             |
|          | Histórico        | Pertence               | 1,1                  | 1,1	                 |                                                             |
|          | Endereco_Aluno   | Pertence               | 1,1                  | 1,n	                 |                                                             |
|          | Aluno_Disciplina | Cursa                  | 1,1                  | 0,n                  |                                                             |	
|          | Telefone_Aluno   | Possui                 | 1,1                  | 0,n                  |                                                             |	
|          | Aluno_Disciplina | Cursa                  | 1,1                  | 0,n	                 |                                                             |

### Entidade 

| Entidade | Relacionamento   | Nome do Relacionamento | Cardinalidade Miníma | Cardinalidade Máxima | Descrição                                                   |
|----------|------------------|------------------------|----------------------|----------------------|-------------------------------------------------------------|
| Curso	   | Aluno	          | Está matriculado       | 1,1                  | 0,n                  | Tabela para cadastro dos cursos oferecidos pela faculdade.  |
|          | Turma            | Gera                   | 1,1                  | 0,n	                 |                                                             |
|          | Departamento     | Controla               | 1,1                  | 1,1	                 |                                                             |
|          | Curso_Disciplina | Possui                 | 1,1                  | 1,n	                 |                                                             |
