## TP2 INFO7015 - Tópicos em Redes de Computadores

#### EXERCÍCIO DE AQUECIMENTO A [10%]:

Para o exercício A foram testados diferentes valores de janela com 10 repetições para cada valor, acrescendo o tamanho de 10 em 10.

A ideia principal foi identificar uma faixa de janela otimizada (melhores valores de potência para cada valor de janela) e posteriormente realizar mais testes dentro dessa faixa para identificar a estabilidade com a janela escolhida.

Podemos observar as variações nos valores de janela e a potência obtida , na Tabela 1. O gráfico que representa o Atraso x Largura de Banda pode ser observado na Figura 1.

##### Tabela 1 - Variações da Janela
<img src="https://image.ibb.co/bZ3WiL/tabela1.png" alt="TP2" border="0"></p>

##### Figura 1 - Largura de Banda (Média) x Atraso
<img src="https://image.ibb.co/jvz43L/graf1.png" alt="TP2" border="0"></p>

A faixa otimizada de janelas ficou entre 10 e 15. Testes com a janela fixada acima de 15 levavam a uma queda na potência, essa tendência pode ser observada na Figura 2.

##### Figura 2 - Potência x Tamanho da Janela
<img src="https://image.ibb.co/jWsriL/graf2.png" alt="TP2" border="0"></p>

Após identificar a faixa de melhores resultados, foram realizadas 40 repetições com as janelas em valor 10, 11, 12, 13, 14, 15 e 16. A potência foi maior com o valor de janela 15. Na tabela 2 podemos observar a estatística descritiva dos dados.

##### Tabela 2 - Estatística descritiva das repetições
<img src="https://image.ibb.co/eM0tQq/estat-a.png" alt="TP2" border="0"></p>

#### Exercício de aquecimento B [40%]:
Para o exercício B foi adicionado um mecanismo simples, tentando replicar o funcionamento do AIMD (additive-increase/multiplicative-decrease). O funcionamento básico do AIMD é atuar sobre o tamanho da janela quando ele se depara com congestionamento. Com base no algoritmo original, fora estipuladas algumas variáveis de controle, sendo as principais uma ação a ser tomada quando se identifica o congestionamento, e um mecanismo de controle para limitar o envio em massa e aumentar gradativamente o tamanho da janela depois do congestionamento.

O algoritmo original foi modificado com base em valores fixos, ele não calcula os valores de redução e acréscimo automaticamente, sendo necessária a configuração no início de cada teste.

Inicialmente o algoritmo foi implementado, posteriormente alguns testes foram realizados nos tamanhos de redução de janela, limite para início do controle de congestionamento e valor de acréscimo da janela, para refinar e obter melhores valores na potência.

Para calibração inicial do algoritmo modificado, foram utilizados os valores do exercício A para identificar o melhor tamanho de janela x Potência, e melhor valor de atraso obtido.

No decorrer dos experimentos os testes foram feitos com valores diferentes ao detectar o congestionamento e também com a mudança nos valores de aumento da janela ao chegar em um determinado limite, conforme observado na tabela 3.

##### Tabela 3 - Testes dos valores da replicação do AIMD
<img src="https://image.ibb.co/hES7OL/AIMD1-dados.png" alt="TP2" border="0"></p>

 Após identificar os melhores valores, testes de estabilidade com os valores ótimos foram realizados, com o objetivo de analisar se os valores são constantes após várias repetições.
 
 A média de 31 repetições foi 22,08. Observou-se que em alguns dos testes a potência caia drásticamente, mesmo sem nenhuma alteração no esquema. Não foi possível identificar a causa dos valores discrepantes, podendo a causa ser o código do esquema ou o sistema de fluxos utilizado na implementação remota.
 
 A estatística das repetições pode ser observada na Tabela 4. O gráfico com os valores das repetições pode ser observado na Figura 3.
 
 ##### Tabela 3 - Estatística descritiva de 30 repetições com valores otimizados
 <img src="https://image.ibb.co/h4wWfq/estat-b.png" alt="TP2" border="0"></p>
 
 ##### Figura 2 - Repetições com valores otimizados - Esquema similar ao AIMD
<img src="https://image.ibb.co/cgHkqq/repeticoesaimd.png" alt="TP" border="0"></p>

#### Exercício D [50%]:

Para o exercício D, foram realizadas melhorias no esquema anterior, com mudanças sutis, mas que permitiram maior variação dos valores assumidos pela janela. O incremento com valores menores (0,1), possibilitou um ajuste mais fino, melhorando sensivelmente a potência, e oferecendo maior estabilidade, conforme visto na Figura 3. 

Outro benefício pode ser obtido por conta da utilização do RTT como variável de controle para o Treshold, ao contrário de simplesmente utilizar um valor fixo como gatilho.

##### Figura 3 - Repetições - Esquema melhorQigual
 <img src="https://image.ibb.co/n8BWHf/repet-c.png" alt="TP2" border="0"></p>
 
Os valores obtidos em 33 repetições foi mais regular quando comparado ao esquema similar ao AIMD simples no exercício B, o que pode ser comprovado na estatística descritiva na Tabela 4. 
 
 ##### Tabela 4 - Estatística descritiva das repetições do modelo melhorQigual
 <img src="https://image.ibb.co/c4Utxf/statc.png" alt="TP2" border="0"></p>


##### Figura 4 - Summary Statistics
 <img src="https://image.ibb.co/euQqtL/power.png" alt="TP2" border="0"></p>

##### Figura 5 -Throughput
 <img src="https://image.ibb.co/n1DYV0/exec-c2.png" alt="TP2" border="0"></p>
 
 ##### Figura 6 -Throughput
 <img src="https://image.ibb.co/jfTBHf/exec-c3.png" alt="TP2" border="0"></p>

#### Exercício E [0%]:
> **melhorQigual**
