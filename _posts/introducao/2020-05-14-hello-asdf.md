---
layout: post
title:  "Hello ASDF"
date:   2020-05-14 22:12:34 -0300
author: Wellington Silva
tag: tutorial
categories: ["introducao"]
---

Uma nova maneira de gerenciar ambiente de programação.
Para demonstração da instalação será usado o ASDF versão `0.7.8.`.
Portanto, recomedo que visite o repositório oficial do [ASDF](https://github.com/asdf-vm/asdf.git) para obter a sua versão mais recente.

~~~bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.7.8

echo -e '\n. $HOME/.asdf/asdf.sh' >> ~/.bashrc
echo -e '\n. $HOME/.asdf/completions/asdf.bash' >> ~/.bashrc

asdf update  
asdf update --head
~~~

Para instalar o plugin de uma linguagem é simples, basta conhecer o repositório da linguagem, que está disponível no repositório oficial do ASDF.
Para demonstrar a instalação de uma linguagem de programação, será usado Golang.

* Primeiro adicione o repositório da linguagem que desejar.
~~~bash
asdf plugin-add golang https://github.com/kennyp/asdf-golang.git
~~~

Precisa listar as versões ersões disponível da linguagem, para isto utilize o seguinte comando:

~~~bash
asdf list-all golang 
~~~

Selecione a versão que desejar, tendo como exemplo a versão 1.14 do Golang
 
~~~bash
asdf install golang 1.14
~~~

Agora, precisa configurar onde será usado a linguagem, caso queira permitir acesso por todo o sistema use o comando:

~~~bash
asdf global golang 1.14
asdf plugin-update --all
~~~

Ou, instale versão local onde a linguagem será empregada, da seguinte forma
~~~bash
asdf local golang 1.14
asdf plugin-update --all
~~~

Conclui que o ASDF tornou o teste compatibilidade de versões das linguagens mais simples e podendo até evitar a criação de ambiente virtuais para o desenvolvimento.

## Referência 
* [ASDF](https://asdf-vm.com/#/)
