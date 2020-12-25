# Java

<div style="text-align:center"><img src="https://upload.wikimedia.org/wikipedia/pt/thumb/3/30/Java_programming_language_logo.svg/1200px-Java_programming_language_logo.svg.png" height="500" /></div>

Java se trata de uma linguagem de programação Orientada a Objetos interpretada e compilada pela JVM (Máquina Virtual Java), onde todo o gerenciamento das aplicações java é realizado.

## Onde Encontrar

<p>O Java, ou melhor, o JDK (Kit de Desenvolvimento Java) pode ser encontrado no site da <a href="https://code.visualstudio.com/">Oracle</a>, onde você pode encontrar as diversas versões do java em seus diversos meios de instalação para cada plataforma. Aqui iremos nos focar apenas na isntalação em máquinas linux</p>

OBS: Recomendamos fortemente que você utilize a versão 8 do Java, pois ainda é a versão mais estável que existe, e roda a grande maioria das aplicações feitas em Java sem complicações, ao contrário das versões mais recentes que sempre apresentam algum tipo de problema em outras aplicações java. Caso queira instalar uma versão mais recente, o tutorial não mudará, mas tenha certeza de que em algum momento você terá complicações relacionadas a versão.

## Como instalar

Você poderá encontrar a versão do java que deseja instalar, no site da Oracle mencionado anteriormente. Escolha a versão entre 32bits (x86) e 64bits (x64) e selecione para baixar. Caso você não possua uma conta Oracle ainda, meus pêsames (Abrir um CNPJ é mais fácil), pois essa é sem dúvidas a parte mais chata de todo esse processo.

#### Passo 1

Para abrir um terminal de qualquer lugar usando `ctrl + alt + t`.

#### Passo 2

Após baixar a versão que você escolher do java vamos remover qualquer possível versão do OpenJDK que exista em sua máquina através do comando abaixo antes de instalar o que foi baixado:

```
sudo apt-get update && apt-get remove openjdk*
```

#### Passo 3

Entre no diretório onde foi baixado o arquivo da JDK. No meu caso, \$HOME/Downloads

```
cd ~/Downloads
```

#### Passo 4

Extraia o arquivo .tar.gz baixado. Basta digitar o comando abaixo e pressionar `Tab` para completar automaticamente com a versão que você baixou.

```
tar -zxvf jdk-
```

#### Passo 5

Vamos agora criar uma diretório em `/opt`, onde ficará isntalada a JDK.

```
sudo mkdir -p /opt/java
```

#### Passo 6

Mova a pasta extraída para o diretório `/opt/java`. No meu caso, o número da versão era 1.8.0_251. Caso a sua versão seja diferente, basta mudar no comando.

```
sudo mv jdk1.8.0_251 /opt/java
```

#### Passo 7

Vamos configurar e instalar o java no sistema com os comandos abaixo:

```
sudo update-alternatives --install "/usr/bin/java" "java" "/opt/java/jdk1.8.0_251/bin/java" 1
sudo update-alternatives --set java /opt/java/jdk1.8.0_251/bin/java
```

Preste bastante atenção a versão que você está utilizando para mudar nos comandos, se necessário.

#### Passo 8

Vamos testar a instalação do java com o comando:

```
$ java -version
java version "1.8.0_251"
Java(TM) SE Runtime Environment (build 1.8.0_251-b08)
Java HotSpot(TM) 64-Bit Server VM (build 25.251-b08, mixed mode)

```

Agora que você já tem o java em sua máquina, você está pronto para sofrer caso esteja programando com qualquer coisa que não seja Spring. Lembre-se, com grandes poderes vem grandes `java.lang.NullPointerException`!
