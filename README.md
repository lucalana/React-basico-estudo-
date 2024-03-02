# BÁSICO REACT

O react ele é declarativo e usa `JSX` por isso que para rodar ele no navegador é necessário
um compilador para transformar os código em `JS`. O react é uma biblioteca do JavaScript
e para pode usar ela temos que instalar `react` e `react-DOM`.

Existe duas coisa diferentes HTML e a DOM, e o que o react altera e manipula é a DOM.
DOM é a representação do HTML através de um objeto.
E dentro dela existe ua hierarquia dos elementos, pai, filho etc.

Alguns conceitos importantes do react

- Components
- Props
- State

A interface pode ser dividida em pequenos pedaços que são chamados de `components`,
assim esse código pode ser reutilizado.
Para criar um componente a função tem que ter primeira letra maiúscula e para usar o component é colocado o nome da função
dentro de tags `<>` fincando dessa forma.

```JSX
function Header() {
  return (<h1>Primeiro Título</h1>)
}

<Header />

```

Além de que é possível utilizar componentes dentro de componentes.

As `props` são usadas dentro do `component` para passar dados e mostrar, manipular o fazer o que for com eles.
É possível passar essa informação para o componente criando um atributo na tag do componente e passando a informação.
No componente ele recebe uma variável como parâmetro que armazena as `props` passadas e nos podemos usar a desestruturação
para pegar cada uma delas. No componente para usar as variáveis e até mesmo JavaScript lá dentro vai ter que usar entre `{}`.

```JSX
function Header({title}) {
  return (<h1>{title}</h1>)
}

<Header title="Título 1" />

```

Dentro dos `components` podemos escutar eventos e tratar eles, dentro de um componente button
nos podemos adicionar o atributo `onCLick` e atribuir uma função para que ao ser clicado ele
execute algo.

```JSX
      function Button({buttonText}) {
        function handleClick() {
          console.log('increment like count');
        }
        return (
          <button onClick={handleClick}>{buttonText}</button>
        )
      }

```

O react tem um conjunto de funções chamadas `hooks`, que vai permitir adicionar lógica
aos componentes e um `state`. O `hook` usado para manipular o `state` no react é o `useState()`.
Ele vai retornar um array e você acessa e pode usar esses valores usando a desestruturação.
O primeiro vai ser o valor e o segundo a função que vamos usar para alterar esse valor e já podemos
inicializar esse valor com 0.

```JSX
     function Button({buttonText}) {
        const [likes, setLikes] = React.useState(0);

        function handleClick() {
          setLikes(likes + 1);
        }
        return (
          <button onClick={handleClick}>{buttonText} {likes}</button>
        )
      }

```
