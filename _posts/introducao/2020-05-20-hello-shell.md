---
layout: post
title:  "Hello Shell"
date:   2020-05-20 00:01:00 -0300
author: Wellington Silva
tag: tutorial
categories: ["introducao"]
---

## Comandos básicos

<table><thead><tr><th>Comando</th><th>Descrição</th><th>Sintaxe</th></tr></thead><tbody><tr><td>echo</td><td>Exibe o texto na tela</td><td>echo “texto a ser mostrado”</td></tr><tr><td>sleep</td><td>Dá um tempo antes de continuar executando</td><td>sleep segundos exemplo: Sleep 1</td></tr><tr><td>read</td><td>Recebe o valor de uma variável (veremos ainda) read variável</td><td>exemplo: read dados</td></tr><tr><td>&gt;</td><td>Escreve num arquivo-texto (apagando o que estava lá)</td><td>echo “texto” &gt; /home/"user"/arquivo</td></tr><tr><td>&gt;&gt;</td><td>Escreve num arquivo-texto (última linha, não apaga)</td><td>echo “texto” &gt; /home/"user"/arquivo</td></tr><tr><td>&amp;</td><td>Roda o comando em 2o plano e continua o script</td><td>Comando &amp;</td></tr><tr><td>exit</td><td>Sai do script</td><td>exit</td></tr><tr><td>touch</td><td>Cria arquivos-texto</td><td>touch nome_do_arquivo</td></tr><tr><td>#</td><td>Comenta tudo depois deste símbolo</td><td># Comentário</td></tr></tbody></table>

## Manipulação de Diretórios
<table><thead><tr><th>Comando</th><th>Descrição</th><th>Sintaxe</th></tr></thead><tbody><tr><td>rm</td><td>-rf rm -rf +diretório</td><td>Deleta arquivos/pastas e tudo que estiver dentro (cuidado)</td></tr><tr><td>pwd</td><td>pwd</td><td>Mostra o caminho do diretório atual</td></tr><tr><td>mkdir</td><td>mkdir nome_pasta</td><td>Cria uma pasta</td></tr><tr><td>ls</td><td>ls</td><td>Mostra os arquivos do diretório atual</td></tr><tr><td>chmod</td><td>chmod 777 arquivo_ou_pasta</td><td>Muda as permissões, 777 = permissão total</td></tr><tr><td>chown</td><td>chown user:grupo arq_ou_diret.</td><td>Muda o proprietário de arquivos e pastas</td></tr><tr><td>cd</td><td>cd diretório</td><td>Entra em diretórios</td></tr></tbody></table>

## Comandos de Usuários
<table><thead><tr><th>Comando</th><th>Descrição</th><th>Sintaxe</th></tr></thead><tbody><tr><td>useradd</td><td>useradd nome_usuario -g alunos (no grupo)</td><td>Adiciona um usuário</td></tr><tr><td>userdel</td><td>userdel usuário</td><td>Deleta usuário e seus arquivos</td></tr><tr><td>groupdel</td><td>groupdel grupo</td><td>Deleta um grupo</td></tr><tr><td>groups</td><td>groups nome_usuario</td><td>Mostra os grupos do usuário</td></tr><tr><td>addgroup</td><td>addgroup usuario grupo ou addgroup nomedogrupo</td><td>Cria um grupo ou adiciona um usuário ao grupo</td></tr><tr><td>sudo</td><td>sudo comando</td><td>Executa comandos como root</td></tr><tr><td>whoami</td><td>whoami</td><td>Identifica com qual usuário você esta logado</td></tr></tbody></table>

## Redes
<table><thead><tr><th>Comando</th><th>Descrição</th><th>Sintaxe</th></tr></thead><tbody><tr><td>ifconfig</td><td>ifconfig</td><td>Mostra as interfaces de rede</td></tr><tr><td>hostname</td><td>hostname</td><td>Mostra ou muda o nome de seu computador na rede</td></tr><tr><td>ping</td><td>Ping</td><td>ip_desejado Dispara pacotes para outro pc, para testar conexões etc</td></tr></tbody></table>

## Manipulação do sistema
<table><thead><tr><th>Comando</th><th>Descrição</th><th>Sintaxe</th></tr></thead><tbody><tr><td>killall</td><td>killall nome_do_programa</td><td>Mata um processo</td></tr><tr><td>xkill</td><td>xkill</td><td>Mata um programa</td></tr><tr><td>whatis</td><td>whatis +nome do programa</td><td>Descreve o que faz o comando</td></tr><tr><td>diff</td><td>diff arquivo1 arquivo2</td><td>Compara os dois arquivos</td></tr><tr><td>ps</td><td>ps -elf</td><td>Mostra os programas que estão rodando</td></tr><tr><td>cat</td><td>cat arquivo_texto</td><td>Mostra o conteúdo de um arquivo de texto</td></tr><tr><td>ln</td><td>ln -s arquivo_original atalho</td><td>Cria atalho</td></tr><tr><td>cp</td><td>cp arquivo destino</td><td>Copia um arquivo ou diretório (-R para diretórios)</td></tr><tr><td>find</td><td>find +nome</td><td>Procura por arquivos e diretórios</td></tr></tbody></table>

# Linguagem Shell 

## Variável

~~~bash 
# Escrever
echo "Hello World"

# Atribuição 
RESPOSTA = $"certo"

# Recebe valor atribuido pelo usuário
echo "Escreve sua resposta"
read RESPOSTA

# Atribuição por arquivo texto
ALUNO=$(cat /home/resposta.txt)
~~~

## Operadores Lógicos

### Comparadores Númericos
* **-lt** Número é menor que (Less Than)
* **-gt** Número é maior que (Greater Than)
* **-le** Número é menor ou igual (Less Equal)
* **-ge** Número é maior ou igual (Greater Equal)
* **-eq** Número é igual (EQual)
* **-ne** Número é diferente (Not Equal)

### Comparadores Alfanuméricos
* **=** Texto é igual
* **!=** Texto é diferente
* **-n** Texto não nulo
* **-z** Texto é nulo

## Operadores de Seleção
~~~bash
# Estrutura If
# Espaçamento obrigatório
if [ "$USER" = "ANA"  ];then
    mkdir $USER
fi

# Estrutura If (...) Else
if [ "$USER" = "ANA"  ];then
    mkdir $USER
    
    else 
        echo "Error: Usuário não existe"
fi

# Estrutura Case
case $TESTE in
    1) echo "Opção 1"
    2) echo "Opção 2"
    *) echo "Opção Inválida"
    exit;; 
esac

~~~

## Laço de repetição
~~~bash
# Estrutura For
for ((LOOP=0; LOOP<3; LOOP++));do 
    echo $LOOP
done

# Estrutura While
LOOP =$"0"  
while [ $LOOP -lt 3 ];do
    echo $LOOP
    $LOOP =$[ $LOOP + 1 ] 
done

# Estrutura Until
LOOP =$"0"  
until [ $LOOP -lt 3 ];do
    echo $LOOP
    $LOOP =$[ $LOOP + 1 ]
done
~~~

## Referência
* https://docs.cs.cf.ac.uk/notes/linux-shell-commands/
* https://swcarpentry.github.io/shell-novice/reference/
* http://linuxcommand.org/index.php