---
# Comparação Experimental de Algoritmos para Cálculo da Mediana
#  Combinada de Duas Listas Ordenadas
---

Raul Santiago Pinheiro e Pedro Albano Lopes Braga

raul.santiago.pinheiro@aluno.ifce.edu.br \|
pedro.albano.lopes05@aluno.ifce.edu.br

Graduação em Ciência da Computação --- Instituto Federal de Educação,
Ciência e Tecnologia do Ceará (IFCE) --- Maracanaú --- CE --- Brasil

# Resumo

Este trabalho apresenta uma comparação experimental entre dois
algoritmos para cálculo da mediana combinada de duas listas ordenadas:
(i) o algoritmo de Juntar e Ordenar (O(n log n)) e (ii) o algoritmo de
Divisão e Conquista (O(log n)). Foram gerados vetores de tamanhos
variando entre 10² e 10⁶ elementos, igualmente espaçados, e medido o
tempo médio de execução de ambos os métodos. Os experimentos foram
executados em ambiente Google Colab PRO+ com GPU H100, permitindo
medições estáveis e reproduzíveis. Os resultados mostram clara vantagem
do algoritmo de Divisão e Conquista para entradas grandes, refletindo
sua melhor complexidade assintótica. Além disso, a equivalência
funcional dos resultados foi validada para todos os casos testados.

Palavras-chave: mediana combinada, algoritmos de busca, análise
experimental, complexidade de algoritmos.

# Abstract

This work presents an experimental comparison between two algorithms for
computing the combined median of two sorted lists: (i) the Merge and
Sort algorithm (O(n log n)) and (ii) the Divide and Conquer algorithm
(O(log n)). Input vectors with sizes ranging from 10² to 10⁶ were
generated and the average execution time of both methods was measured.
The experiments were carried out in a Google Colab PRO+ environment with
an NVIDIA H100 GPU, providing stable and reproducible measurements. The
results show a clear advantage of the Divide and Conquer algorithm for
large inputs, reflecting its better asymptotic complexity. Furthermore,
the functional equivalence of the results was validated for all tested
cases.

Keywords: combined median, search algorithms, experimental analysis,
algorithm complexity.

# 1. Introdução

O cálculo da mediana de duas listas ordenadas é um problema clássico em
ciência da computação, com aplicações em estatística, análise de dados e
aprendizado de máquina. Existem diferentes abordagens para resolver esse
problema, que variam quanto à complexidade assintótica e custo prático
de execução. Este artigo apresenta um estudo experimental comparando
duas dessas abordagens: o algoritmo de Juntar e Ordenar e o algoritmo de
Divisão e Conquista. A relevância desse estudo está na compreensão da
diferença prática entre algoritmos com ordens de crescimento distintas,
sobretudo em um ambiente de execução de alto desempenho.

# 2. Metodologia

## 2.1 Algoritmos

Foram comparadas duas abordagens: (i) Juntar e Ordenar, que consiste em
concatenar as listas e ordená-las para encontrar a mediana, e (ii)
Divisão e Conquista, que utiliza partições binárias para encontrar a
mediana de forma eficiente em O(log n).

## 2.2 Geração dos Dados

Foram gerados vetores de tamanhos n igualmente espaçados entre 100 e
1.000.000. Para cada tamanho, foram criadas 10 instâncias distintas de
dados, com valores inteiros pseudo-aleatórios simulando salários. Os
mesmos vetores foram utilizados para os dois algoritmos, garantindo uma
comparação justa.

## 2.3 Procedimento

Para cada tamanho de entrada n:\
1. Geraram-se duas listas ordenadas de tamanho n.\
2. Aplicaram-se os dois algoritmos sobre as mesmas entradas.\
3. Mediu-se o tempo de execução médio usando time.perf_counter().\
4. Validou-se a equivalência dos resultados numéricos entre ambos.

## 2.4 Ambiente de Teste

Os experimentos foram realizados em um ambiente Google Colab PRO+ com
GPU H100, utilizando CPU virtualizada Intel Xeon (12 núcleos / 24
threads), arquitetura x86_64, 38.5 MiB de cache L3 e suporte a
instruções AVX-512. O sistema utiliza virtualização KVM e foi executado
com Python 3.12 e biblioteca matplotlib 3.9. Este ambiente oferece alta
estabilidade e capacidade para executar experimentos com tamanhos de
entrada elevados.

# 3. Resultados

A Figura 1 apresenta o tempo médio de execução dos algoritmos em função
do tamanho das entradas. Observa-se que o algoritmo de Divisão e
Conquista cresce muito mais lentamente, confirmando sua vantagem teórica
para grandes volumes de dados. Nenhuma divergência foi observada nos
resultados numéricos.

![Figura 1 --- Tempo médio de execução dos dois algoritmos em ambiente
Colab PRO+ com GPU H100.](./Figura 1.jpeg)

# 4. Discussão

Os resultados obtidos confirmam que, embora ambos os algoritmos
apresentem resultados corretos e tempo de execução razoável para
tamanhos pequenos, a diferença se torna significativa para entradas
grandes. O custo de ordenar a lista combinada cresce em O(n log n),
enquanto o método de Divisão e Conquista permanece em O(log n) no menor
vetor. Essa diferença se manifesta claramente no gráfico obtido.

O uso de um ambiente com GPU H100 e CPU Xeon contribuiu para garantir
estabilidade e tempo de execução reduzido, mas não altera a tendência
teórica: o algoritmo de Divisão e Conquista apresenta superioridade
prática em cenários de larga escala.

# 5. Conclusão e Trabalhos Futuros

Este artigo apresentou uma análise experimental comparando duas
abordagens para o cálculo da mediana combinada de duas listas ordenadas.
Os resultados mostram que, para entradas grandes, a abordagem de Divisão
e Conquista é significativamente mais eficiente, enquanto o método de
Juntar e Ordenar permanece competitivo apenas para entradas menores.
Como trabalhos futuros, pretende-se avaliar variações com listas de
tamanhos distintos, cenários de paralelização e implementações
diretamente otimizadas para GPU.

# Referências Bibliográficas

-   CORMEN, T. H.; LEISERSON, C. E.; RIVEST, R. L.; STEIN, C.
    Introduction to Algorithms. 3. ed. MIT Press, 2009.

-   BENTLEY, J. L. Programming Pearls. Addison-Wesley, 1986.

-   HOARE, C. A. R. Quicksort. The Computer Journal, v. 5, n. 1, p.
    10--15, 1962.

-   SEDGEWICK, R.; WAYNE, K. Algorithms. 4. ed. Addison-Wesley, 2011.

-   KNUTH, D. E. The Art of Computer Programming, Vol. 3: Sorting and
    Searching. Addison-Wesley, 1998.
