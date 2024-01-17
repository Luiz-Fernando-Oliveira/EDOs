# Encontrando a estabilidade de um sistema de Equações Diferenciais Ordinárias usando Python

As soluções do seguinte sistema de EDOs são estáveis?

y′1=−y1+y2
y′2=−2y2

A fim determinar se as soluções desse sistema são estáveis, devemos analisar os autovalores da matriz de coeficientes. Se pelo menos um dos autovalores tiver a parte real positiva o sistema será instável, mas caso sejam todos os autovalores não positivos (sua parte real), as soluções são consideradas estáveis, isto é, as soluções permanecem limitadas e controladas ao longo do tempo, convergindo para valores finitos ou para um estado de equilíbrio estável à medida que o tempo avança, mesmo diante de perturbações ou variações nas condições iniciais, exibindo um comportamento previsível.

Para verificar isso, seria necessário encontrar as raízes do polinômio característico de uma matriz que resulta da subtração da matriz de coeficientes pela matriz resultante da multiplicação de cada autovalor pela matriz identidade da mesma ordem. Em nosso exemplo, essa matriz é:

[(−1, −λ0)
(1, −2−λ)]

Onde λ representa o autovalor.
No entanto, usando a biblioteca numpy do Python conseguimos os autovalores diretamente, conforme o código abaixo:

import numpy as np

# Define a matriz de coeficientes
A = np.array([[-1, 1], [0, -2]])

# Calcula os autovalores
autovalores = np.linalg.eigvals(A)

# Verifica a parte real dos autovalores
partes_reais = np.real(autovalores)

# Imprime os autovalores e suas partes reais
print("Autovalores:", autovalores)
print("Partes reais:", partes_reais)
Ao executar esse código, obtemos os autovalores e suas partes reais. O resultado do exemplo fornecido pelo Python foi:

Autovalores: [-1. -2.]
Partes reais: [-1. -2.]
No exemplo acima, os autovalores são -1 e -2, e suas partes reais são -1 e -2, respectivamente. Ambas as partes reais são negativas, o que significa que todas as soluções do sistema de equações são estáveis.

Portanto, com base na análise dos autovalores, podemos concluir que as soluções do sistema de EDOs fornecido são estáveis.
