# L4.1G.Adria_marques_da_silva

1. O contêiner é o elemento pai que organiza os outros elementos. Os itens são os filhos diretos desse contêiner. A propriedade display: flex deve ser colocada no contêiner.

2. Se o CSS não definir flex-direction, o eixo principal será horizontal, da esquerda para a direita, porque o valor padrão é row.

3. A sobra de espaço é a parte que fica vazia depois que os itens ocupam seus tamanhos iniciais. Quando todos têm flex-grow: 0, podemos usar justify-content para distribuir ou posicionar os itens no contêiner.

4. O valor padrão de flex-grow é 0, o que significa que o item não cresce para ocupar o espaço que sobra.

5. Na analogia da pizza, a mesa representa o contêiner, o prato representa o tamanho inicial de cada item, a sobra representa o espaço vazio e o peso do flex-grow representa a parte que cada item recebe na divisão.

6.Para a marca ocupar todo o espaço que sobra, usamos flex-grow: 1 nela. Assim, a marca cresce, enquanto os links continuam com o tamanho do texto.

.marca {
    flex-grow: 1;
}

7.Temos três itens com base zero em uma faixa de 600px, com pesos 2, 3 e 1.

Soma dos pesos:

2 + 3 + 1 = 6

Valor de uma parte:

600 ÷ 6 = 100px

Largura de cada item:

Primeiro: 2 × 100 = 200px.

Segundo: 3 × 100 = 300px.

Terceiro: 1 × 100 = 100px.

8.Os três itens começam com 100px cada, e a faixa tem 600px. Os valores de flex-grow são 0, 1 e 2.

Soma dos tamanhos iniciais:

100 + 100 + 100 = 300px

Sobra:

600 − 300 = 300px

Soma dos pesos:

0 + 1 + 2 = 3

Valor de uma parte:

300 ÷ 3 = 100px

Largura final:

Primeiro: 100 + 0 = 100px.

Segundo: 100 + 100 = 200px.

Terceiro: 100 + 200 = 300px.

9. O flex-shrink entra em ação quando falta espaço para os itens na faixa. Seu valor padrão é 1, permitindo que os itens encolham para caber no espaço disponível.

10. Temos dois itens de 400px em uma faixa de 600px.

Soma dos tamanhos:

400 + 400 = 800px

Espaço que falta:

800 − 600 = 200px

Como os dois itens têm flex-shrink: 1 e o mesmo tamanho inicial, dividem a redução igualmente:

200 ÷ 2 = 100px

Largura final:

Primeiro: 400 − 100 = 300px.

Segundo: 400 − 100 = 300px.

11. Se o primeiro item tiver flex-shrink: 0, ele não encolhe e continua com 400px. O segundo item precisa diminuir para compensar a falta de espaço.

Primeiro: 400px.

Segundo: 400 − 200 = 200px.

Soma:

400 + 200 = 600px

Portanto, o conjunto cabe exatamente na faixa, desde que o segundo item consiga encolher até 200px.

12. Um exemplo é um ícone ao lado de um texto. Podemos usar flex-shrink: 0 no ícone para impedir que ele fique achatado quando faltar espaço. Assim, o texto é que encolhe para que os dois continuem organizados.

13. O flex-basis define o tamanho inicial do item antes de ele crescer ou encolher. Se o item tem width: 200px e flex-basis: 10rem, vale o flex-basis. Considerando que 1rem equivale a 16px, 10rem são 160px. 

14. Porque flex-basis: 0 faz os itens começarem com tamanho zero. Assim, o flex-grow divide todo o espaço disponível entre eles, em vez de dividir apenas a sobra.

15. A tabela fica assim:

**| Atalho | Grow | shrink| Basis |**
|---|---|---|---|
| flex: initial | 0 | 1 | auto |
| flex: 1 | 1 | 1 | 0 |
| flex: auto | 1 | 1 | auto |
| flex: none | 0 | 0 | auto |

16. Com flex: 1:

600 ÷ 2 = 300px para cada item.

Resultado: 300px e 300px.
Com flex: auto:

Soma: 100 + 300 = 400px.

Sobra: 600 − 400 = 200px.

Cada item recebe 100px.

Resultado: 200px e 400px

Os resultados são diferentes porque `flex: 1` começa do zero, enquanto `flex: auto` começa do tamanho do conteúdo.

17. Falso. flex: 1 começa com base zero, enquanto flex: auto começa com o tamanho do conteúdo. Porém, quando os conteúdos têm o mesmo tamanho e as condições são iguais, os dois podem produzir o mesmo resultado.

18. A propriedade padrão min-width: auto pode impedir que o item fique menor que seu conteúdo. Para resolver, usamos min-width: 0, permitindo que ele encolha mais.

19. Isso pode acontecer em uma página com menu lateral e texto quando existe uma palavra muito longa que não quebra. O texto pode ultrapassar os limites da página.

20.

a) A ordem visual será C, A, B, porque C tem order: -1.

b) A ordem de foco ao apertar Tab continuará sendo A, B, C, seguindo a ordem do HTML.

c) Isso importa porque a ordem visual pode ser diferente da ordem de navegação. Isso pode confundir pessoas que usam o teclado ou leitores de tela.


21. O valor padrão de order é 0. O item com order: -1 aparece antes do item com order: 2, porque o menor número aparece primeiro.


22.

align-self: flex-end: o item fica no final do eixo cruzado e não estica.

align-self: auto: o item segue o align-items do pai e, nesse caso, estica.

23. Usamos align-self para alinhar um único item de forma diferente. Já align-items serve para alinhar todos os itens do contêiner.


24. Os itens de .pagina são header, .miolo e footer. Os itens de .miolo são aside e main.

25. Porque .miolo também precisa ser um contêiner flex para colocar o menu e o texto lado a lado. Ser um item de .pagina não faz dele automaticamente um contêiner.

26.
- `display: flex`: transforma a página em um contêiner flex.
- `flex-direction: column`: organiza o topo, o miolo e o rodapé em coluna.
- `min-height: 100vh`: faz a página ter, no mínimo, a altura da tela.
- `.miolo { display: flex; }`: coloca o menu e o texto lado a lado.
- `flex: 1` no `.miolo`: faz o miolo ocupar o espaço vertical que sobra.
- `aside { flex: 0 0 10rem; }`: mantém o menu com largura de 10rem, sem crescer nem encolher.
- `main { flex: 1; }`: faz o texto ocupar o espaço horizontal restante.
- `min-width: 0`: permite que o texto encolha sem ultrapassar os limites da página.


  27. O erro é colocar flex-grow no contêiner, porque essa propriedade controla o crescimento dos itens. A correção é colocá-la no filho que deve crescer, usando flex-grow: 1, por exemplo.
 

28. Duas formas de resolver são:

Usar min-width: 0 quando um texto longo impede o item de encolher.

Usar flex-shrink: 0 quando um ícone ou botão precisa manter seu tamanho, deixando os outros itens cederem espaço


29.

flex-basis: define o tamanho inicial do item.

flex-grow: determina como o item recebe o espaço que sobra.

flex-shrink: determina como o item encolhe quando falta espaço.

order: muda a ordem visual dos itens.

align-self: permite alinhar um item individualmente no eixo cruzado.
