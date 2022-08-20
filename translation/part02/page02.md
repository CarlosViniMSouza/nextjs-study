## **Atualizando a interface do usuário com métodos JavaScript e DOM**

Vamos ver como você pode usar métodos JavaScript e DOM adicionando uma tag `h1` ao seu projeto.

Abra seu editor de código e crie um novo arquivo `index.html`. Dentro do arquivo HTML, adicione o seguinte código:

```HTML
<!-- index.html -->
<html>
    <body>
        <div></div>
    </body>
</html>
```

Em seguida, dê ao `div` um `id` exclusivo para que você possa segmentá-lo mais tarde.

```HTML
<!-- index.html -->
<html>
    <body>
        <div id="app"></div>
    </body>
</html>
```

Para escrever JavaScript dentro de seu arquivo HTML, adicione uma tag `script`:

```HTML
<!-- index.html -->
<html>
    <body>
        <div id="app"></div>
        <script type="text/javascript"></script>
    </body>
</html>
```

Agora, dentro da tag `script`, você pode usar um método DOM, `getElementById()`, para selecionar o elemento `<div>` pelo seu `id`:

```HTML
<!-- index.html -->
<html>
    <body>
        <div id="app"></div>
        <script type="text/javascript">

            const app = document.getElementById("app");

        </script>
    </body>
</html>
```

Você pode continuar usando métodos DOM para criar um novo elemento `<h1>`:

```HTML
<!-- index.html -->
<html>
<body>
    <div id="app"></div>
    <script type="text/javascript">
        // Selecione o elemento div com id 'app'
        const app = document.getElementById("app");

        // Crie um novo elemento H1
        const header = document.createElement("h1");

        // Crie um novo nó de texto para o elemento H1
        const headerContent = document.createTextNode(
            "Develop. Preview. Ship. 🚀",
        );

        // Anexar o texto ao elemento H1
        header.appendChild(headerContent);

        // Coloque o elemento H1 dentro da div
        app.appendChild(header);
    </script>
</body>
</html>
```

Para certificar-se de que tudo está funcionando, abra o arquivo HTML no navegador de sua escolha. Você deve ver uma tag h1 que diz: 'Desenvolver. Visualizar. Embarcar. 🚀'.

## **HTML vs DOM**

Se você observar os elementos DOM dentro das [ferramentas de desenvolvedor do navegador](https://developer.chrome.com/docs/devtools/overview/), notará que o DOM inclui o elemento `<h1>`. O DOM da página é diferente do código-fonte - ou em outras palavras, do arquivo HTML original que você criou.

![img-01](https://nextjs.org/static/images/learn/foundations/source-code.png)

Isso ocorre porque o HTML representa o **conteúdo inicial da página**, enquanto o DOM representa o **conteúdo atualizado da página** que foi alterado pelo código JavaScript que você escreveu.

Atualizar o DOM com JavaScript simples é muito poderoso, mas detalhado. Você escreveu todo esse código para adicionar um elemento `<h1>` com algum texto:

```HTML
<!-- index.html -->
<script type="text/javascript">
  const app = document.getElementById('app');
  const header = document.createElement('h1');
  const headerContent = document.createTextNode('Develop. Preview. Ship. 🚀');

  header.appendChild(headerContent);
  app.appendChild(header);
</script>
```

À medida que o tamanho de um aplicativo ou equipe cresce, pode se tornar cada vez mais desafiador criar aplicativos dessa maneira.

Com essa abordagem, os desenvolvedores gastam muito tempo escrevendo instruções para dizer ao computador **como** ele deve fazer as coisas. Mas não seria legal descrever **o que** você quer mostrar e deixar o computador descobrir **como** atualizar o DOM?
