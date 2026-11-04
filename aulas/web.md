# Web: página acessível com interação

[Voltar ao índice](../README.md)

**Público:** iniciantes · **Duração:** 2 aulas de 50 minutos.

## Objetivos e pré-requisitos

Construir uma página com HTML semântico, estilo responsivo e um evento em JavaScript. Use navegador e editor de texto. O exemplo funciona como arquivo local, sem instalar bibliotecas.

## Explicação para a aula

> “O HTML organiza o conteúdo, o CSS controla sua apresentação e o JavaScript responde às interações. Cada camada tem uma responsabilidade, mas as três trabalham juntas.”

## Prática guiada

Crie uma pasta `oficina-web`, salve o exemplo abaixo como `index.html` e abra o arquivo no navegador.

```html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Oficina de TI</title>
  <style>
    body { margin: 0; font: 1rem/1.6 system-ui, sans-serif; background: #f1f5f9; color: #0f172a; }
    main { max-width: 44rem; margin: 2rem auto; padding: 1.5rem; }
    article { background: white; padding: 1.5rem; border-radius: 1rem; }
    button { padding: .75rem 1rem; border: 0; border-radius: .5rem; background: #1e40af; color: white; font: inherit; cursor: pointer; }
    button:focus-visible { outline: 3px solid #0f172a; outline-offset: 3px; }
  </style>
</head>
<body>
  <main>
    <h1>Oficina de Tecnologia da Informação</h1>
    <article aria-labelledby="titulo">
      <h2 id="titulo">Meu primeiro projeto web</h2>
      <p>Estrutura, apresentação e comportamento em uma única atividade.</p>
      <button id="concluir" type="button">Marcar atividade como concluída</button>
      <p id="resultado" role="status"></p>
    </article>
  </main>
  <script>
    const botao = document.querySelector("#concluir");
    const resultado = document.querySelector("#resultado");
    botao.addEventListener("click", () => {
      resultado.textContent = "Atividade concluída. Agora explique o que você aprendeu!";
    });
  </script>
</body>
</html>
```

**Resultado esperado:** o botão atualiza a mensagem sem recarregar a página. Ao atualizar o navegador, a mensagem desaparece: este exemplo não persiste dados. O conteúdo com `role="status"` oferece um mecanismo para anunciar atualizações a tecnologias assistivas.

## Verificação manual

- Abra a página em uma janela estreita e confirme que o texto continua legível.
- Use Tab para focar o botão e Enter para ativá-lo.
- Confira o idioma da página e a hierarquia h1/h2.
- Abra as ferramentas do navegador e confira se há erros no console.

## Desafios e entrega

1. Personalize os textos com um tema de TI.
2. Separe o CSS em `style.css` e o JavaScript em `script.js`.
3. Adicione um botão “Reiniciar” que limpe a mensagem.
4. Documente objetivo, execução e limitações em um README.

Entregue os arquivos, uma captura da página e a lista de verificações realizadas. Use conteúdo fictício e não inclua dados pessoais.

<details>
<summary>Resolução comentada</summary>

- No head, use `<link rel="stylesheet" href="style.css">`; transfira apenas as regras para o CSS.
- Use `<script src="script.js" defer></script>` no head e transfira apenas o código JavaScript para o arquivo externo. `defer` permite executá-lo após a análise do HTML.
- O novo botão deve usar `type="button"`; no evento de clique, defina `resultado.textContent = ""`.
- A estrutura semântica comunica a organização do conteúdo; o foco visível ajuda quem navega por teclado.

</details>

## Avaliação formativa

Peça ao estudante que identifique onde alterar um título, uma cor e uma ação. Avalie a capacidade de explicar as três camadas com a [rubrica docente](../GUIA-DOCENTE.md).
