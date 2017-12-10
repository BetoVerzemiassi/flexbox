# Aula 01 - Introdução ao flexbox e fazendo o cabeçalho

# Quais as principais diferenças entre as nossas propriedades de posicionamento?

1) display: inline;

2) display: inline-block;

3) float: left | right;

4) display: flex;


**display: inline**

* Colocando `display: inline` nos elementos permite eles se posicionarem um do lado do outro, o problema do `display: inline` é que os elementos não aceitam mais que seja modificada tanto a width quanto a height. Isso limita MUITO nossas possibilidades.

**display: inline-block**

* O `display: inline-block` permite os elementos se posicionarem um do lado do outro porém, diferentemente do `display: inline` ele permite que os elementos tenham sua width e height modificadas. Por esse motivo o `display: inline-block` é muito mais interessante na maioria dos casos do que o `display: inline.`

* O problema de usar `display: inline-block` é espaçar os elementos entre si. Para fazer isso teríamos que colocar margins e fazer contas.

**float: left | right**

* O `float` é mais complicado, ele empurra o elemento para um dos lados (left | right) e os elementos que estão em baixo sobem. Isso nem sempre é o que a gente quer. Além do mais o float não permite que usemos a propriedade `vertical-align: middle` para alinhar os elementos verticalmente. Ou seja, para contornar isso uma possibilidade seria ter que colocar `margin-top` ou `bottom` nos elementos e usar os temidos números mágicos!

**display: flex**

* O `display: flex` veio com o intuito de facilitar nossa vida nesses aspectos de posicionamento. Ele permite os elementos ficarem um do lado do outro, permite espaçar os elementos de forma mais intuitiva e sem ter que fazer cálculos. Além disso ele também permite alinhar os elementos verticalmente de forma fácil.

* O `display flex` pode ser um pouco mais complicado de usar tendo em vista que existem diversas propriedades que vem junto da especificação flexible box, todavia tudo isso foi feito para justamente melhorar nosso código.


**Usando a propriedade flex**

* Digamos que temos o seguinte código:

```
<section class="pai">
  <div class="filho">Primeiro filho</div>
  <div class="filho">Segundo filho</div>
</section>
```

* Como poderiamos fazer com flex para que os elementos filhos ficassem um do lado do outro?

```
.pai{
    display: flex;
}
```

> Basta colocarmos `display: flex` no elemento pai. Dessa forma os filhos já ficariam um do lado do outro.


# Vimos no primeiro exercício dessa aula que podemos espaçar os elementos que tem o pai com a propriedade `display: flex` de forma fácil.

* Veja o seguinte exemplo:

```
<header class="cabecalho">
  <a class="logo" href="#">
    <img src="img/logo.png">
  </a>

  <ul class="menu">
    <li class="menu-item">Item 1 do menu</li>
    <li class="menu-item">Item 2 do menu</li>
    <li class="menu-item">Item 3 do menu</li>
    <li class="menu-item">Item 4 do menu</li>
  </ul>
</header>
```

* Como podemos fazer com que o menu fique do lado direito e o logo do lado esquerdo?

* Primeiro devemos colocar `display: flex` no pai, para isso fariamos:

```
.cabecalho {
  display: flex;
}
```

* Agora automaticamente o `.logo` e o `.menu` ficam um do lado do outro.

* Dessa forma deve sobrar bastante espaço à direita deles. Para alocar todo esse espaço que está a direita para ficar entre eles devemos colocar a propriedade

> `justify-content: space-between`

* No `.cabecalho`, ou seja, no pai.

* O código para isso ficaria assim:

```
.cabecalho {
  display: flex;
  justify-content: space-between;
  align-items: center; //alinha todos os elementos verticalmente
}
```

> **align-items: center** faz com que os elementos dentro do pai que está com flex se alinhem verticalmente, portanto, pra eles ficarem alinhados no centro podemos usar `align-items: center`, colocando essa propriedade no pai dos elementos que queremos alinhar, no caso `.cabecalho`


# Aula 02 - Fazendo o footer e controlando melhor os elementos

* Podemos distribuir os elementos dentro do pai de diversas formas, podemos por exemplo:

* Colocar todo espaço à esquerda, jogando o conteúdo para direita com **justify-content: flex-end**

* Colocar todo o espaço à direita, jogando o conteúdo para esquerda com **justify-content: flex-start** (padrão)

* Colocar todo espaço à direita, jogando o conteúdo para o meio com **justify-content: center**

* Colocar todo espaço entre os elementos como vimos antes usando **justify-content: space-between**

* Colocar o espaço em volta dos elementos usando **justify-content: around**