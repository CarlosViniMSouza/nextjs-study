## **Como criar IU com componentes**

As interfaces do usuário podem ser divididas em blocos de construção menores chamados componentes.

Os componentes permitem que você crie trechos de código reutilizáveis ​​e independentes. Se você pensar em componentes como **peças LEGO**, você pode pegar essas peças individuais e combiná-las para formar estruturas maiores. Se você precisar atualizar uma parte da interface do usuário, poderá atualizar o componente ou bloco específico.

![img-01](https://nextjs.org/static/images/learn/foundations/components.png)

Essa modularidade permite que seu código seja mais sustentável à medida que cresce, pois você pode facilmente adicionar, atualizar e excluir componentes sem tocar no restante do nosso aplicativo.

O bom dos componentes React é que eles são apenas JavaScript. Vamos ver como você pode escrever um componente React, de uma perspectiva JavaScript:

## **Criando Componentes**

Em React, componentes são funções. Dentro da sua tag de `script`, escreva uma função chamada `header`:

```HTML
<script type="text/jsx">
    const app = document.getElementById("app");

    function header() {
        return (<h1>Develop. Preview. Ship! 🚀</h1>);
    }

    ReactDOM.render(header, app)
</script>
```

Mas, espere um segundo. Se você tentar executar o código acima em seu navegador, receberá um erro. Para que isso funcione, há duas coisas que você precisa fazer:

Primeiro, os componentes React devem ser capitalizados para distingui-los de HTML e JavaScript simples.

```JS
function Header() {
    return <h1>Develop. Preview. Ship! 🚀</h1>
}

// Capitalize o componente React
ReactDOM.render(Header, app);
```

Segundo, você usa componentes React da mesma forma que usaria tags HTML normais, com colchetes angulares `<>`.

```JS
function Header() {
    return <h1>Develop. Preview. Ship! 🚀</h1>
}

// Capitalize o componente React
ReactDOM.render(<Header/>, app);
```

## **Componentes de aninhamento**

Os aplicativos geralmente incluem mais conteúdo do que um único componente. Você pode **aninhar** componentes React dentro uns dos outros como faria com elementos HTML normais.

No seu exemplo, crie um novo componente chamado `HomePage`:

```JS
function Header() {
    return <h1>Develop. Preview. Ship. 🚀</h1>;
}

function HomePage() {
    return <div></div>;
}

ReactDOM.render(<Header/>, app);
```

Em seguida, aninhe o componente `<Header>` dentro do novo componente `<HomePage>`:

```JS
function Header() {
    return <h1>Develop. Preview. Ship. 🚀</h1>;
}

function HomePage() {
    return (
        <div>
            {/* Alinhando o componente do cabeçalho*/}
            <Header/>
        </div>
    )
}
```
