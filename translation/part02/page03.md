## **Começando com React**

Para usar o React em seu projeto, você pode carregar dois scripts React de um site externo chamado `unpkg.com`:

° **react** é a biblioteca principal do React.

° **react-dom** fornece métodos específicos do DOM que permitem que você use o React com o DOM

Em vez de manipular diretamente o DOM com JavaScript simples, você pode usar o método `ReactDOM.render()` do `react-dom` para dizer ao React para renderizar nosso título `<h1>` dentro de nosso elemento `#app`.

## **O que é JSX?**

JSX é uma extensão de sintaxe para JavaScript que permite que você descreva sua interface do usuário em uma sintaxe familiar semelhante a HTML. O bom do JSX é que, além de seguir [três regras do JSX](https://beta.reactjs.org/learn/writing-markup-with-jsx#the-rules-of-jsx), você não precisa aprender nenhum novo símbolo ou sintaxe fora do HTML e do JavaScript.

Observe que os navegadores não entendem o JSX imediatamente, então você vai precisar de um compilador JavaScript, como um [Babel](https://babeljs.io/), para transformar seu código JSX em JavaScript normal.

## **Adicionando Babel ao seu projeto**

Para adicionar o Babel ao seu projeto, copie e cole o seguinte script em seu arquivo `index.html`:

```HTML
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```

Além disso, você precisará informar ao Babel qual código transformar alterando o tipo de script para `type=text/jsx`.

```HTML
<html>

<body>
    <div id="app"></div>

    <!-- Add ReactJS to Project -->
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>

    <!-- Add Babel to Project -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <script type="text/jsx">
        const app = document.getElementById("app");

        ReactDOM.render(<h1>Develop. Preview. Ship. 🚀</h1>, app);
    </script>
</body>

</html>
```

Você pode então executar seu código no navegador para confirmar que está funcionando corretamente.

Você pode começar a ver como, usando o React, você pode reduzir muito código repetitivo.

E é exatamente isso que o React faz, é uma biblioteca que contém trechos de código reutilizáveis ​​que executam tarefas em seu nome - neste caso, atualizando a interface do usuário.


**NOTA**: Você não precisa saber exatamente como o React atualiza a UI para começar a usá-la, mas se quiser saber mais, dê uma olhada nas [árvores da UI](https://beta.reactjs.org/learn/preserving-and-resetting-state#the-ui-tree) e nas seções do [método de renderização](https://beta.reactjs.org/reference/render) na Documentação do React.
