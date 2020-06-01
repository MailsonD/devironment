# Git

<div style="text-align:center"><img src="https://git-scm.com/images/logo@2x.png" /></div>

O Git se trata de um sistema para controle de versões distribuído e de código aberto, para lidar com todo tipo de projeto, seja ele de pequeno ou grande porte. Os sistemas mais popualres utilizados em conjunto com o git são **BitBucket, GitLab e o GitHub**.

## Onde Encontrar

Em sistemas linux, o git é comumente instalando através de um instalador binário, o que pode ser feito através de um ou mais comandos dependendo da distro linux que você estiver utilizando.

## Como Instalar

Em sistemas baseados em **Debian**, como o Ubuntu e o Mint, o git pode ser instalado através de apt-get (ou apenas apt, nas versões mais recentes), através do comando abaixo.

```
sudo apt-get install git-all
```

Em distros como o Fedora, no entanto, ele pode ser instalado utilizando o yum, através do comando abaixo.

```
sudo yum install git-all
```

## Como Configurar

A primeira coisa a se fazer após instalar o git é configurar seu nome e endereço de email, pois cada commit realizado com o git utilizará estas informações como sua **identidade**. Para isso, podemos utilizar os comandos abaixo.

```
git config --global user.name "Meu Nome"
git config --global user.email meunome@email.com
```

Após isso, podemos listar as configurações do git para verficiar se está tudo correto usando:

```
git config --list --show-origin
```

## Bonus

Grande parte da comunidade que utiliza o git, costuma utilizar o **GitHub** como principal plataforma para aramazenamento de seus repositórios remotos. Porém, nem todos sabem que é possível linkar a sua conta no github ao git da sua máquina diretamente através de **SSH**, para que não seja necessária a autenticação a cada comando remoto para o repositório.

Para fazermos isso, basta seguir alguns pequenos passos listados abaixo.

#### Passo 1

É necessário gerar uma chave SSH no seu computador para que possamos utilizá-la na nossa conta do github. É possível também ver se você já possui uma chave SSH no seu computador fazendo o seguinte:

```
cd ~/.ssh
ls
```

O resultado deve ser algo tipo:

```
authorized_keys2     id_dsa       knwn_hosts
config               id_dsa.pub
```

Basta procurar por um par de arquivos chamados por `id_dsa` ou `id_rsa` e que tenham um equivalete com a extensão `.pub`. O arquivo `.pub` é a sua chave pública do SSH, e o correspondente é a sua chave privada.

Caso o diretório ~/.ssh não exista, siga para o **Passo 2**

Caso você já possúa este par de arquivos, incluindo o `.pub`, pule para o **Passo 3**.

#### Passo 2

Para criar sua chave SSH, utilizamos o `ssh-keygen`, o qual é pelo pacote SSH presente nos sistemas Linux/macOS.

No terminal, basta rodar o comando:

```
ssh-keygen -o
```

Primeiro, confirme onde você quer salvar a sua chave (Por padrão `.ssh/id_rsa`), e caso você não deseje por uma senha para a sua chave, basta pressionar enter mais duas vezes, ele deve gerar sua chave.

A saída deve ser algo tipo:

```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/schacon/.ssh/id_rsa):
Created directory '/home/schacon/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/schacon/.ssh/id_rsa.
Your public key has been saved in /home/schacon/.ssh/id_rsa.pub.
The key fingerprint is:
d0:82:24:8e:d7:f1:bb:9b:33:53:96:93:49:da:9b:e3 schacon@mylaptop.local
```

#### Passo 3

Agora que nossa chave SSH foi gerada, podemos enfim utilizá-la. Para isso, vamos ler o resultado da chave primeiro com o comando:

```
cat ~/.ssh/id_rsa.pub
```

E o resultado da sua chave deve aparecer de maneira parecida com:

```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAklOUpkDHrfHY17SbrmTIpNLTGK9Tjom/BWDSU
GPl+nafzlHDTYW7hdI4yZ5ew18JH4JW9jbhUFrviQzM7xlELEVf4h9lFX5QVkbPppSwg0cda3
Pbv7kOdJ/MTyBlWXFCR+HAo3FXRitBqxiX1nKhXpHAZsMciLq8V6RjsNAQwdsdMFvSlVK/7XA
t3FaoJoAsncM1Q9x5+3V0Ww68/eIFmb1zuUFljQJKprrX88XypNDvjYNby6vw/Pb0rwert/En
mZ+AW4OZPnTPI89ZPmVMLuayrD2cE86Z/il8b+gw3r3+1nKatmIkjn2so1d01QraTlMqVSsbx
NrRFi9wrf+M7Q== schacon@mylaptop.local
```

Esta é a sua chave SSH, e agora podemos enfim utilizá-la na nossa conta do github

#### Passo 4

Vá até as configurações da sua conta no github. Lá, procure por uma aba com o nome **SSH and GPC keys**.

Procure então por um botão para adicionar uma nova chave SSH. Ponha o título que você desejar para se referir ao seu computador, e então adicione a sua chave SSH que você acabou de gerar.

Com isso feito, já podemos realizar nossas operações remotas sem a necessidade de fazer login a cada operação. **Lembre-se**, sempre que for clonar um repositório a partir de agora, selecione a opção de clonar com ssh, para que o repositório possa reconhecer sua chave durante as operações remotas.

Tenha um bom trabalho =)
