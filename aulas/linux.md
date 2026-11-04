# Linux: arquivos e diagnóstico básico

[Voltar ao índice](../README.md)

**Público:** iniciantes · **Duração:** 2 aulas de 50 minutos.

## Objetivos e pré-requisitos

Navegar em diretórios, criar e copiar arquivos, interpretar permissões e registrar informações básicas do ambiente. Use Bash em Linux, máquina virtual ou WSL já preparado para a aula. Não é necessário acesso de administrador.

## Explicação para a aula

> “O terminal permite descrever uma sequência de ações. Antes de executar um comando, precisamos saber em qual pasta estamos, quais arquivos serão afetados e qual resultado esperamos.”

Caminhos absolutos partem da raiz `/`; caminhos relativos dependem do diretório atual. Permissões distinguem leitura, escrita e execução para proprietário, grupo e outros usuários.

## Prática guiada

Use uma pasta de laboratório nova. Os comandos abaixo criam arquivos de exemplo e não exigem `sudo`.

```bash
mkdir laboratorio-ti
cd laboratorio-ti
pwd
mkdir documentos backup
printf "Linux na prática\n" > documentos/anotacoes.txt
cp documentos/anotacoes.txt backup/
ls -l documentos backup
cat documentos/anotacoes.txt
wc -l documentos/anotacoes.txt
uname -s
df -h .
```

**Resultado esperado:** existem duas pastas, cada uma com uma cópia de `anotacoes.txt`. O conteúdo contém uma linha. `df -h .` apresenta o uso do sistema de arquivos onde está a pasta atual, com unidades legíveis. A saída varia conforme o computador.

## Laboratório: relatório do ambiente

Crie o arquivo `relatorio.sh` no editor, dentro de `laboratorio-ti`:

```bash
#!/usr/bin/env bash
printf "Sistema: "
uname -s
printf "\nDiretório atual:\n"
pwd
printf "\nEspaço do sistema de arquivos atual:\n"
df -h .
printf "\nArquivos do laboratório:\n"
ls -l documentos backup
```

Execute `bash relatorio.sh`. Compare cada seção com o comando executado separadamente. O script deve ser executado a partir da pasta `laboratorio-ti`, pois usa caminhos relativos.

## Desafios e entrega

1. Acrescente outra linha ao arquivo original. A cópia muda automaticamente? Justifique.
2. Compare `pwd`, `ls` e `cat`: qual pergunta cada comando responde?
3. Leia uma linha de `ls -l` e identifique o proprietário, o grupo e as permissões.
4. Acrescente ao relatório a quantidade de linhas das anotações.

Entregue o script, uma saída de exemplo e uma explicação sobre os caminhos usados. Revise a saída antes de publicá-la, retirando nomes ou caminhos pessoais.

<details>
<summary>Resolução comentada</summary>

- `cp` cria uma cópia independente; alterar o original não sincroniza o backup.
- `pwd` informa onde estamos; `ls` lista entradas; `cat` mostra o conteúdo de arquivos.
- Em uma permissão como `-rw-r--r--`, o primeiro caractere indica arquivo comum; os três grupos seguintes representam proprietário, grupo e outros.
- Adicione `wc -l documentos/anotacoes.txt` ao relatório e compare a contagem com o arquivo aberto no editor.

</details>

## Avaliação formativa

Solicite que a dupla preveja o resultado antes de executar cada comando. Avalie a interpretação das saídas e a organização do relatório com a [rubrica docente](../GUIA-DOCENTE.md).
