# Barnes-Hut
Trabalho de paralelização através de OpenMP do algoritmo Barnes Hut.

## Motivação
O objetivo consiste na adaptação do algoritmo Barnes Hut, utilizado na 14th Marathon of Parallel Programming para um modelo que explore as possibilidades de paralelismo existentes.

## Definição
A implementação consistiu em: 
* Alterar a execução das funções calcule_center_mass x e y, permitindo que ambas pudessem ser executadas em paralelo, visto que não tinham dependência de dados; 
* Utilizar um loop paralelo para a execução interna do laço na função update_forces (o qual foi o maior responsável pela diminuição do tempo de execução do algoritmo); 
* Utilizar outro loop paralelo para execução do laço do cálculo de velocidade e posição.

## Rodando o algoritmo
```
gcc barnes_hut.c -fopenmp -o barnes_hut -lm
time ./barnes_hut 100 galaxy.in 16
```

## Resultados obtidos:
* Sequêncial (sem alterações no código): 5m25,205s
* 16 threads: 1m10,743s
* 8 threads: 1m13,643s
* 4  threads: 1m30,799s
* 2 threads: 2m37,631s
