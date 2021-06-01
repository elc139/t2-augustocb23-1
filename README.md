[Programação Paralela](https://github.com/AndreaInfUFSM/elc139-2021a) > Trabalhos

# T2: Experiências com Profilers


## Parte 1

Pré-requisitos: esta parte foi prevista para ser realizada em Linux com ambiente GNU (GCC, make, etc.). Variações disso são possíveis para quem gosta de viver perigosamente :smile:. 

1. Instale os pacotes `valgrind` e `kcachegrind`. Eles costumam estar disponíveis nas distribuições mais conhecidas de Linux. A instalação costuma ser tranquila, pois não é preciso compilar nenhum desses pacotes :angel:. 

2. Abra o programa [dotprod_seq.c](dotprod_seq/dotprod_seq.c), que contém o código fonte de um programa simples para calcular o produto escalar de 2 vetores. 
Veja que este programa permite configurar o tamanho dos vetores e o número de repetições do cálculo, para variar a carga de trabalho.

3. Compile o programa:

   ```
   make
   ```

4. Execute o programa com uma configuração "pequena", por exemplo:

   ```
   ./dotprod_seq 3000 20
   ```

5. Execute o programa com uma configuração maior, por exemplo:

   ```
   ./dotprod_seq  30000000 90
   ```

6. Agora execute o programa com o valgrind/callgrind para coletar dados sobre a execução:
   ```
   valgrind --tool=callgrind --dump-instr=yes --simulate-cache=yes --collect-jumps=yes ./dotprod_seq 3000 20
   ```
   Veja que foi gerado um arquivo ao final da execução.

7. Abra o arquivo gerado no kcachegrind. Explore as diferentes opções da interface gráfica. São intuitivas para você?! Procure documentação técnica sobre as diferentes opções, para certificar-se sobre o que está sendo exibido. Lembre que a execução do programa deve ter sido bem rápida.


8. Repita o uso de valgrind/kcachegrind para outras entradas do programa, observando o que muda nos perfis gerados. Guarde informações sobre cada uso (parâmetros de entrada e arquivos de saída).

9. Responda:
    - (a) Como o perfil é afetado pelas entradas do programa?
    - (b) Pelo perfil de execução, há alguma função que poderia ser candidata a melhoria de desempenho? Por quê?



## Parte 2


+ Escolha um programa que você tenha desenvolvido, ou cujo código seja familiar para você. Pode ser um programa em qualquer linguagem, de preferência estruturado em vários subprogramas (procedimentos, funções, métodos...), e que possa ter a entrada variada facilmente.

+ Escolha 2 profilers para a linguagem alvo e procure repetir os passos da Parte 1, adequando-os a possíveis diferenças.

+ Observe e faça anotações sobre: 
   - (a) particularidades de instalação, recursos ou funcionamento dos profilers, 
   - (b) resultados obtidos e 
   - (c) dúvidas e/ou dificuldades encontradas.


## Entrega

No seu repositório de entrega, crie um documento `Entrega.md`, contendo:
 - Identificação completa da disciplina e do aluno
 - Seções separadas para a Parte 1 e a Parte 2;
 - Links para arquivos, respostas, anotações, screenshots e quaisquer outras observações adicionais sobre cada um dos itens das Partes 1 e 2;
 - Referências.



