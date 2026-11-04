# Git e GitHub: do primeiro commit à colaboração

[Voltar ao índice](../README.md)

**Público:** iniciantes · **Duração:** 2 aulas de 50 minutos.

## Objetivos e pré-requisitos

Ao final, o estudante deverá explicar o papel do Git, registrar alterações e integrar uma branch. Use Git instalado, terminal e editor de texto. A prática principal é local; o GitHub entra no desafio de colaboração.

## Explicação para a aula

> “Salvar um arquivo mantém a versão atual. O Git permite registrar etapas do projeto e entender o que mudou entre elas. O Git funciona no computador; o GitHub hospeda repositórios e oferece recursos de colaboração.”

Um commit registra uma versão do conteúdo preparado no índice. Uma branch permite desenvolver uma sequência de alterações sem mudar imediatamente a linha principal.

## Prática guiada

Execute em uma pasta nova, usando Bash ou Git Bash. Antes do primeiro commit, confira se nome e e-mail já estão configurados no Git. Use um e-mail apropriado para os commits; eles podem se tornar públicos ao publicar o repositório.

```bash
mkdir oficina-git
cd oficina-git
git init -b main
printf "# Oficina de Git\n" > README.md
git status
git add README.md
git commit -m "docs: inicia apresentação da oficina"
git switch -c melhoria-readme
printf "\nObjetivo: compreender o histórico do projeto.\n" >> README.md
git diff
git add README.md
git commit -m "docs: descreve objetivo da oficina"
git switch main
git merge melhoria-readme
git log --oneline --graph --all
git status
```

**O que observar:** antes de `git add`, há alterações ainda não preparadas. Depois do commit, essas alterações foram registradas. O merge integra a melhoria na branch main. Ao final, o status deve indicar que não há alterações pendentes.

## Desafios e entrega

1. Crie a branch `exemplos`, acrescente uma seção de exemplos e integre-a à main.
2. Explique a diferença entre salvar, preparar e fazer commit.
3. No GitHub, crie um repositório de estudo vazio, siga as instruções exibidas para conectar o remoto e envie seus commits. Nunca inclua senhas ou tokens nos arquivos.
4. Em dupla, proponha uma alteração por pull request e escreva uma revisão que explique o motivo de uma sugestão.

Entregue o histórico resumido, o status final e um parágrafo justificando suas mensagens de commit. Para o desafio remoto, inclua o link do pull request.

<details>
<summary>Resolução comentada</summary>

- Use `git switch -c exemplos`, edite o README, prepare com `git add README.md`, registre com `git commit` e volte à main antes de `git merge exemplos`.
- Salvar altera o arquivo no disco; preparar seleciona conteúdo para o próximo commit; fazer commit registra esse conteúdo no histórico local.
- Um pull request apresenta uma proposta de integração e permite discutir e revisar as alterações.
- Mensagens como “arrumei” dizem pouco; “docs: adiciona exemplos de comandos” comunica a finalidade.

</details>

## Avaliação formativa

Peça ao estudante que mostre uma alteração no diff antes de registrá-la. Se ele apenas repetir comandos, solicite que explique o que espera ver no próximo status. Use a [rubrica docente](../GUIA-DOCENTE.md).
