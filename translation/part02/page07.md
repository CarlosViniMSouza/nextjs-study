## Exibindo dados com adereços

Até agora, se você reutilizasse seu componente `<Header />`, ele exibiria o mesmo conteúdo nas duas vezes.

```JS
function Header() {
    return <h1>Develop. Preview. Ship. 🚀</h1>;
}

function HomePage() {
    return (
        <div>
            <Header />
            <Header />
        </div>
    );
}
```

Mas e se você quiser passar um texto diferente ou não souber as informações com antecedência porque está buscando dados de uma fonte externa?

Elementos HTML regulares têm atributos que você pode usar para passar informações que alteram o comportamento desses elementos. Por exemplo,
alterar o atributo `src` de um elemento `<img>` altera a imagem que é mostrada. Alterar o atributo `href` de uma tag `<a>` altera o destino do link.

Da mesma forma, você pode passar informações como propriedades para componentes React. Estes são chamados de `props`.

![img-01](https://nextjs.org/static/images/learn/foundations/props.png)

Semelhante a uma função JavaScript, você pode projetar componentes que aceitam argumentos personalizados (ou adereços) que alteram o comportamento do componente ou o que é visivelmente mostrado quando é renderizado na tela. Então, você pode passar esses adereços de componentes pai para componentes filho.

**Nota:** No React, os dados fluem pela árvore de componentes. Isso é conhecido como *fluxo de dados unidirecional*. State, que será discutido na próxima seção, pode ser passado de componentes pai para filho como props.
