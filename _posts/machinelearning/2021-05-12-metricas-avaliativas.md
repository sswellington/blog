---
layout: post
title:  "Métricas Avaliativas"
date:   2021-05-12 19:30:34 -0300
author: Wellington Silva
tag: machine learning
categories: ["Machine Learning"]
mathjax: true
---


## Matriz de Confusão

Para se medir a qualidade de um classificador utiliza-se um outro conjunto de teste rotulado(diferente daquele empregado em seu treinamento) e solicita-se a classificação de cada instância desse segundo conjunto de forma individual. 
Os acertos e os erros do classificador são anotados em uma matriz, denominada matriz de confusão, a Tabela abaixo ilustra a matriz de confusão, no qual apresenta um exemplo de matriz
de confusão para um conjunto de dados que possui apenas dois rótulos L = {Positivo,Negativo}.


|                  	| Real Positivo 	| Real Negativo 	|
|:-----------------:|:-----------------:|:-----------------:|
| Predito Positivo 	|       TP      	|       FP      	|
| Predito Negativo 	|       FN      	|       TN      	|

<br> 

A matriz ilustra os índices de acerto e erro de um classificador, detalhando o que foi classificado como Positivo e realmente o é, denominado de Verdadeiro Positivo (TP), e o Negativo que foi rotulado como Positivo, denominado Falso Positivo (FP). 
Além disso, a matriz indica os dados Positivos classificados como Negativos, os chamados Falso Negativos (FN), e as instâncias Negativas realmente rotuladas como tal, os Verdadeiros Negativos (TN).

Por intermédio da matriz de confusão pode-se obter diversos índices e métricas de qualidade que avaliam o desempenho dos classificadores.


## Métricas Avaliativas

* **Revocação ou Sensibilidade:** Mede a proporção de verdadeiros positivos (TP) com relação a todos os positivos

$$ 
   
    Revocação = Sensibilidade = \frac{TP}{TP + FN} 
$$

* **Precisão ou Confiança:** Denota a proporção de verdadeiros positivos (TP) considerando todas as instâncias rotuladas como positivas

$$

    \textit{Precisão} = \textit{Confiança} =\frac{TP}{TP + FP}
$$


* **Especificidade ou Seletividade:** Mede a proporção de verdadeiros negativos (TN) com
relação às instâncias preditas negativas

$$

    \textit{Especificidade} =  \textit{Seletividade} = \frac{TN}{TN + FP}
$$


* **Acurácia:** Mostra o acerto global do classificador como uma proporção de resultados verdadeiros entre o número total de casos examinados.

$$

    \textit{Acurácia} = \frac{TN+TP}{TN + TP + FN + FP}
$$

* **F-Measure:** Combinam as medidas de Precisão e Revocação em uma média harmônica, focada nos exemplos positivos e nas previsões corretas.

$$


$$

* **MSE e MAE:** Quantificam os acertos das previsões. 
O Mean Squared Error (MSE) usa o erro quadrático médio e o Mean Absolute Error (MAE) usa a diferença absoluta entre a classe real e a predita, 

$$

    \textit{\textit{F-Measure}} = 2 * \left( 
        \frac{\textit{Precisão} * \textit{Revocação}}{\textit{Precisão} + \textit{Revocação}} 
    \right)
$$


* **Coeficiente Cohen–Kappa:** Avalia os níveis de concordância entre dois conjuntos de rótulos 

$$

    \kappa = \left( \frac{\lambda_o - \lambda_e} {1 - \lambda_e} \right) =  1 - \left( \frac{1 - \lambda_o} {1 - \lambda_e} \right),
$$


Onde $$\lambda_o$$ é a taxa de aceitação relativa e $$\lambda_e$$ simboliza a taxa hipotética de aceitação.
Explicitamente, $$\lambda_o = ( \frac{TP+TN}{\eta} )$ e $$\lambda_e = (\frac{TP+FP}{\eta} \cdot \frac{TP+FN}{\eta}) + (\frac{FN+TN}{\eta} \cdot \frac{FP+TN}{\eta})$$, $$\eta$$ sendo o tamanho do conjunto de testes.


O Coeficiente de Cohen-Kappa permite interpretar a qualidade de um classificador em termos semânticos.
A Tabela abaixo apresenta o intervalo de valores do Coeficiente de Cohen-Kappa associado ao nível de concordância semântica.


| Coeficiente de Kappa-Cohen    |    Nível de Concordância 	|
|:-----------------------------:|:-------------------------:|
|                 0           	|        Pobre           	|
|          0,00 - 0,2          	|        Leve              	|
|          0,21 - 0,4         	|   Considerável           	|
|          0,41 - 0,6          	|   Moderada              	|
|          0,61 - 0,8          	|   Substancial            	|
|          0,81 - 1,0          	|   Excelente             	|



## Conclusão 
Por último, usar simplesmente um único valor de qualidade pode ser enganoso, recomendando também aplicar outras formas de avaliações, como a curva de Característica do Operador do Receptor  (ROC).
Essa curva ilustra como o número de exemplos positivos corretamente classificados varia de acordo com o número de exemplos negativos classificados incorretamente.
A curva ROC utiliza as métricas de *Revocação* e a *Especificidade* para sua elaboração, onde cada ponto na curva ROC representa um par de *Revocação* e *Especificidade*.
Logo, é importante utilizar mais de uma métrica de avaliativa para verificar a qualidade da classificação, de maneira, a evitar qualquer tipo de visão excessivamente otimista do desempenho de um classificador. 


## Referência 
* [Combinando abordagens supervisionadas e não supervisionadas para segmentação de imagens de úlceras em membros inferiores](https://github.com/sswellington/trabalho-final-de-curso)

---

* [AGGARWAL, C. C. Data mining: The Textbook. Springer, 2015. ISBN 978-3-319-14142-8.](https://rd.springer.com/book/10.1007/978-3-319-14142-8)
* [CONGALTON, R. G.; GREEN, K. Assessing the accuracy of remotely sensed data: principles and practices, 3rd Edition. CRC Press, 2019. ISBN 978-1498776660.](crcpress.com/Assessing-the-Accuracy-of-Remotely-Sensed-Data-Principles-and-Practices/Congalton-Green/p/book/9781498776660)
* [FACELI, K.; CARVALHO, A. C. de; SOUTO, M. C. de. Cluster ensemble and multi-objective clustering methods. In: Pattern Recognition Technologies and Applications: Recent Advances. IGI Global, 2008. p. 325–343.](https://www.igi-global.com/chapter/cluster-ensemble-multi-objective-clustering/28037)
* [POWERS, D. M. W. Evaluation: from precision, recall and f-measure to roc, informedness, markedness and correlation. Journal of Machine Learning Technologies, Bioinfo Publications, v. 2, n. 1, p. 37–63, 2011.](http://hdl.handle.net/2328/27165)
* [PROVOST, F. J. et al. The case against accuracy estimation for comparing induction algorithms.In: International Conference on Machine Learning. [s.n.], 1998. v. 98, p. 445–453](https://pdfs.semanticscholar.org/7770/3a2783f64dfceb638aa9eebd9c9c501bb835.pdf)
* [SIM, J.; WRIGHT, C. C. The Kappa Statistic in Reliability Studies: Use, Interpretation, and Sample Size Requirements. Physical Therapy, v. 85, n. 3, p. 257–268, Mar 2005.](http://dx.doi.org/10.1093/ptj/85.3.257)
* TOWNSEND, J. T. Theoretical analysis of an alphabetic confusion matrix. Perception & Psychophysics, Springer, v. 9, n. 1, p. 40–50, 1971.
