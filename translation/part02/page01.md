## **Renderizando interfaces de usuário**

Para entender como o React funciona, primeiro precisamos de um entendimento básico de como os navegadores interpretam seu código para criar interfaces de usuário interativas (UI).

Quando um usuário visita uma página da web, o servidor retorna um arquivo HTML para o navegador que pode ter esta aparência:

![img-01](https://nextjs.org/static/images/learn/foundations/html-to-dom.png)

O navegador então lê o HTML e constrói o "Document Object Model"(DOM -> Modelo de Objeto de Documento).

## **O que é o DOM?**

O DOM é uma representação de objeto dos elementos HTML. Ele atua como uma ponte entre seu código e a interface do usuário e possui uma estrutura semelhante a uma árvore com relacionamentos pai e filho.

![img-02](https://nextjs.org/static/images/learn/foundations/dom-to-ui.png)

Você pode usar métodos DOM e uma linguagem de programação, como JavaScript, para *ouvir eventos do usuário e [manipular o DOM selecionando](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents), adicionando, atualizando e excluindo elementos específicos na interface do usuário*. A manipulação do DOM permite não apenas segmentar elementos específicos, mas também *alterar seu estilo e conteúdo*.
