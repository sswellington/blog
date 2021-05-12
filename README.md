# Introdução

O Jekyll é um framework web destinado a construção site estático simples e client-side. Tendo como o exemplo de aplicação do Jekyll a elaboração de blog, para sites pessoais. Tom Preston-Werner é o seu criador e utilizou o Ruby on Rails.

O Ruby Rails ganhou popularidade por intermédio de seu criador David Heinemeier Hansson (DHH) em sua palestra "How to build a blog engine in 15 minutes with Ruby on Rails - Como construir um gerenciador de blog em 15 minutos com Ruby on Rails no Brasil em 2005.  

Todos utilizam a  linguagem de programação Ruby, que é caracterizado por ser interpretada multiparadigma, de tipagem dinâmica e forte. Seu criador é Yukihiro Matsumoto em 1995. 

# Configuração 

## Pré-requisito
A linguagem Ruby instalada, caso ainda não tenha, adicione a utilizando o [ASDF](https://sswellington.github.io/blog/2020/05/14/asdf.html) da seguinte forma:

~~~bash
asdf update | asdf update --head
asdf plugin-add ruby https://github.com/asdf-vm/asdf-ruby.git
asdf install ruby 2.7.1
asdf local ruby 2.7.1
asdf plugin-update --all
~~~

## Jekyll
Para instalar o Jekyll basta utilizar o seguinte comando:

~~~bash
gem install bundler jekyll
~~~

Criando o seu primeiro site usando Jekyll:
~~~bash
jekyll new nome-do-site
cd nome-do-site
bundle exec jekyll serve
~~~

Pronto, basta acessar http://127.0.0.1:4000/ e conferir o seu site funcionando.

Comandos básicos: 
~~~bash
bundle install
bundle update
~~~

Utilizando tema: 
Há sites especializados em temas para o Jekyll, no qual pode-se citar os seguintes:
* jamstackthemes.dev
* jekyllthemes.org
* jekyllthemes.io
* jekyll-themes.com

Neste site foi escolhi o `jekyll-theme-dark-reader` para instalo e preciso seguir as instruções abaixo:

1. Fazer download ou clone do repositório
   `git clone https://github.com/sharadcodes/jekyll-theme-dark-reader.git`
2. Abra a pasta
   `cd jekyll-theme-dark-reader`
3. Execute 
   `bundle install`
4. Inicie o servidor Jekyll
   `bundle exec jekyll serve`
5. Acesse o endereço: http://127.0.0.1:4000/
6. Altere o arquivo `_config.yml`  e informe seus dados
    * Endereço onde seu site será hospedado:
        * url: "https://sswellington.github.io"
    * Base da aplicação    
        * baseurl: "/blog"
7. Faça Upload do arquivos em seu repositório.

## Post
Para escrever um artigo é necessário criar um arquivo na pasta `all_collections/_posts` tendo o nome do arquitvo do formato padrão de `AAAA-MM-DD-nome-do-post.md`.
Dentro do arquivo é necessário seguir o padrão de cabeçalho.

> ---
>
> layout: post
>
> title:  Título do texto
>
> date:   2020-05-19 15:12:34 -0300
>
> author: Seu nome
>
> tag: ...
>
> ---
>
> Aqui é escrito o texto.

Por fim, toda alteração feita em seu site necessitário que utilize o comando `bundle install` e `bundle exec jekyll serve`, o primeiro para que o Jekyll faça alteração no site e o segundo para enviar as alterações para o servidor HTTP.

# Referência 
* [Tale](https://github.com/chesterhow/tale/)
* [jekyllrb](https://jekyllrb.com/)
* [jekyll-docs](https://jekyllrb.com/docs/home)
* [jekyll-gh](https://github.com/jekyll/jekyll)
* [jtemporal](https://jtemporal.com/do-tema-ao-ar/)
