# Introdução

## O que significa CSS?
* Cascading Style Sheet
* Código para criar estilos no HTML
* HTML é a estrutura e o CSS é a beleza
* Não é uma linguagem de programação
* É uma linguagem style sheets

## Vamos ao exemplo
* https://codepen.io/pen/

# Comentários
* Não irá afetar o código
* Ajuda a lembrar blocos de códigos
* Deixa dicas para leitura
* Ajuda a entender o código
* Sempre lembrar de fechar um comentário aberto

Comentários começam com `/*`  e termina com `*/`

Abaixo exemplos de utilização de comentários para entendimento da utilização no CSS

```CSS
/* Básico */
/* ------------------ */
body {
    font: 1em/150% Helvetica, Arial, sans-serif;
    padding; 1em;
    margin: 0 auto;
    max-width: 33em;
}
@media (min-width: 70em){
    /* Let's special case the global font size. On large screen or window, we increase the font size for better readbility*/
    body {
        font-size: 130%;
    }
}
h1 {font-size: 1.5em;}

/* Elementos específicos */
/* ------------------ */
 div p, #id:first-line{
     background-color: red;
     border-radius: 3px;
 }
 div p{
     margin: 0;
     padding: 1em;
 }

* A estrutura de comentários para CSS também podem ser utilizadas para desabilitar uma parte do código
Exemplo: 

/*div p{
    margin: 0;
    padding: 1em;
 }*/ 
```
# Anatomia
Como criar o CSS e realizar a associação com o HTML

```CSS
h1 {
    color: blue;
    font-size: 60px;
    background: grey;
}
```
* Selector
* Declaration
* Properties
* Property value

# Seletores (selectors)

Conecta um elemento HTML com o CSS

## Tipos
* Global selector `*`, será aplicado para todos os elementos;
* Element/Type selector `h1, h2, p, div`;
* ID selector `#box, #container`;
* Class selector `.red, .m-4`;
* Attribute selector, Pseudo-class, Pseudo-element, e outros

# Box model

* Você irá perceber que quase tudo são caixas do CSS;
* Posicionamentos, tamanhos, espaçamentos, bordas, cores;
* Caixa pode ficar ao lado de uma outra, ou acima;
* Elementos HTML são caixas;

Exemplo de Box Model aplicado no HTML com CSS:
```HTML
<h1>Evolua Rápido</h1>
<p>Descrição</p>
<button>Embarcar</button>
```
```CSS
h1{
    border: 1px solid red;
    margin: 120px;
    padding: 60px;  
}
```

# Adicionando CSS

## inLine
* Atributo `style`

## <style>
* Tag HTML que irá conter o CSS

## <link>
* arquivo CSS externo

## @import
* arquivo CSS externo

# Cascata (cascading)

A escolha do browser de qual regra aplicar, caso haja muitas regras para o mesmo elemento.

* Seu estilo é lido de cima para baixo.

É levado em consideração 3 fatores:

1. Origem do estilo
2. Especificidade
3. Importancia

### Origem do estilo

inLine > tag style > tag link

### Especificidade

É um cálculo matemático, onde, cada tipo de seletor e origem do estilo, possuem valores a serem considerados.

0. Universal selector, combinators e negation pseudo-class (:not())
1. Element type selector e pseudo-elements (::before, ::after)
10. Classes attribute selectors ([type="radio"])
100. ID selectors
1000. InLine

### Regra !important
* Cuidade, evite o uso
* Não é considerado uma boa prática
* Quebra o fluxo natural da cascata

# At-rules
* Está relacionado ao comportamento do CSS
*começa com o sinal `@` seguido do identificador e valor

## Exemplos comuns

- @import /* incluir um CSS externo */
- @media /* regras condicionais para dispositivos */
- @font-face /*fontes externas */
- @keyframes /* Animation */

```CSS
@import "http://local.style.css";

@media (min-width:500px){
    /*rules here*/
}

@font-face{
    /*rules here*/
}

@keyframes nameofanimation {
    /*rules here*/
}
```

# Shorthand
* Junção de propriedades
* resumido
* legivel

```CSS
/*background properties*/
h1{
    background-color: #000;
    background-image: url(images/bg.gif);
    background-repeat: no-repeat;
    background-position: left top;
}
/*background shorthand*/
h1{
    background: #000 url(images/bg.gif) no-repeat left top;
}
```
# Detalhes
* não irá considerar propriedades anteriores a linha do Shorthand
* valores não especificados assumirão valores padrão
* geralmente, a ordem descrita não importa, mas, se houver muitas propriedades com valores semelhantes, poderá ocorrer problemas

## Propriedades que aceitam shorthand

https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties


# Funções
* Nome seguido de abre e fecha parentesis
* Recebe argumentos

## Exemplos
```CSS
@import url("https://urlaqui.com/style.css");

{
    color: rgb(255, 0, 100);
    width: calc(100% - 10px);
}
```
# DevTools

Chrome DevTools is a set of web developer tools built directly into the Google Chrome browser. DevTools can help you edit pages on-the-fly and diagnose problems quickly, which ultimately helps you build better websites, faster.
Open DevTools
There are many ways to open DevTools, because different users want quick access to different parts of the DevTools UI.

When you want to work with the DOM or CSS, right-click an element on the page and select Inspect to jump into the Elements panel. Or press Command+Option+C (Mac) or Control+Shift+C (Windows, Linux, Chrome OS).
When you want to see logged messages or run JavaScript, press Command+Option+J (Mac) or Control+Shift+J (Windows, Linux, Chrome OS) to jump straight into the Console panel.

# Cuidados com a escrita
Verificar sempre os erros de sintaxe para evitar falhas de estilização.

# Vendor prefixes
Permite que browsers adicione `features` a fim de colocar em uso alguma novidade que vemos no CSS

## Exemplo
```CSS
p{
    -webkit-background-clip: text; /* Chrome, Safari, iOS e Android */
    -moz-background-clip: text; /* Mozilla (Firefox)*/
    -ms-background-clip: text; /* Internet Explorer*/
    -o-background-clip: text; /* Opera*/
}
```
## Consultas

.[http://ireade.github.io/which-vendor-prefix].
.[http://caniuse.com].

