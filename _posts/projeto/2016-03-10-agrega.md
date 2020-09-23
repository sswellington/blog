---
layout: post
title:  "Agrega"
date:   2016-03-10 16:54:34 -0300
author: Wellington Silva
tag: projeto
categories: ["SVC"]
---

[Github](https://github.com/sswellington/agrega)

---

## Objetivo
* Desenvolver Ad Hoc de Sistema de Visão Artificial - SVA   para  extrair   as  seguintes informações das imagens de concreto tratado por meio de  solução  de  fenolftaleína.  (realce  da  pasta,  que  se apresenta "avermelhada"):
* Área relativa ocupada pelos agregados (percentual);
* Extensão linear da interface pasta/agregado (em pixels);
* Representar a quantidade de agregados presentes em uma amostragem de concreto  

## Sumário 
* Segmentação das camadas de cores, logo obter imagem monocromática 
![Red - Blue](https://github.com/sswellington/agrega/blob/main/assets/rb.png?raw=true)

* Análise de histograma
![Histograma](https://github.com/sswellington/agrega/blob/main/assets/histograma.png?raw=true)

* Transformação da imagem monocromática para binária 
![Binária](https://github.com/sswellington/agrega/blob/main/assets/binaria_complemento.png?raw=true)

* Morfologia matemática
![Morfologia matemática](https://github.com/sswellington/agrega/blob/main/assets/mask.png?raw=true)


* Detecção de borda
![Prewitt](https://github.com/sswellington/agrega/blob/main/assets/prewitt.png?raw=true)


* Agregados presentes em uma amostragem de concreto  
![Resultado](https://github.com/sswellington/agrega/blob/main/assets/resultado.png?raw=true "Resultado")

