# T2 - ELC 139

Augusto César Bisognin
Sistemas de Informação - UFSM
ELC139 (Programação Paralela)

## Parte 1

1. Ao analisar as execuções do programa, pude perceber que os resultados seguiam um certo padrão de acordo os parâmetros. Quando alterava o primeiro parâmetro, o programa gastava praticamente o mesmo tempo realizando as multiplicações. Ao aumentar o número de repetições, o custo do `for` tinha um leve aumento.


![3000-90](img/3000-90.png) ![3000-900](img/3000-900.png)

>Execuções com os parâmetros `3000 90` e `3000 900`, respectivamente

2. O principal custo da aplicação estava na linha 40 das imagens acima. O programa realiza uma multiplicação e somas os resultados. Visto que a ordem das multiplicações não alteraria o resultado, seria possivel paralelizar essa operação sem muitas alterações no código.
