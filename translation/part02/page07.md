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

## **Usando adereços**

Em seu componente `HomePage`, você pode passar um prop de `title` personalizado para o componente `Header`, assim como você passaria atributos HTML:

```JS
function HomePage() {
  return (
    <div>
      <Header title="React 💙" />
    </div>
  );
}
```

E `Header`, o componente filho, pode aceitar esses adereços como seu primeiro `parâmetro de função`:

```JS
function Header(props) {
   return <h1>Develop. Preview. Ship. 🚀</h1>
}
```

Se você `console.log()` props, você pode ver que é um **objeto** com uma propriedade título.

```JS
function Header(props) {
   console.log(props) // { title: "React 💙" }
//   return <h1> React 💙 </h1>
}
```

Como props é um objeto, você pode usar a **desestruturação de objetos** para nomear explicitamente os valores de props dentro dos parâmetros de sua função:

```JS
function Header({ title }) {
   console.log(title) // "React 💙"
//   return <h1>React 💙</h1>
}
```

Então você pode substituir o conteúdo da tag `<h1>` pela sua variável de título.

```JS
function Header({ title }) {
   console.log(title);
   return <h1>title</h1>;
}
```

Se você abrir seu projeto no navegador, verá que ele está exibindo a palavra "title". Isso ocorre porque o React pensa que você pretende renderizar uma string de texto simples para o DOM.

Você precisa de uma maneira de denotar ao React que esta é uma variável JavaScript.

## **Iterando por listas**

É comum ter dados que você precisa mostrar como uma lista. Você pode usar métodos de matriz para manipular seus dados e gerar elementos de interface do usuário com estilo idêntico, mas que contêm informações diferentes.

**Nota:** React não tem opinião quando se trata de busca de dados, o que significa que você pode escolher a solução que melhor se adapta às suas necessidades. Mais tarde, discutiremos as [opções de busca de dados](https://nextjs.org/learn/basics/data-fetching) em Next.js. Mas, por enquanto, você pode usar um array simples para representar dados. 

Adicione uma matriz de nomes ao seu componente `HomePage`:

```JS
function HomePage() {
  const names = [
    'Ada Lovelace', 
    'Grace Hopper', 
    'Margaret Hamilton'
  ];

  return (
    <div>
      <Header title="Develop. Preview. Ship. 🚀" />
    </div>
  );
}
```

Você pode então usar o método `array.map()` para iterar sobre o array e usar uma **função de seta** para mapear um nome para um item de lista:

```JS
function HomePage() {
  const names = [
    'Ada Lovelace', 
    'Grace Hopper', 
    'Margaret Hamilton'
  ];

  return (
    <div>
      <Header title="Develop. Preview. Ship. 🚀" />
      <ul>
        {
          names.map((name) => (
            <li>
              {name}
            </li>))
        }
      </ul>
    </div>
  );
}
```
