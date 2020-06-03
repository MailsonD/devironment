## Docker

<div style="text-align:center"><img src="https://www.docker.com/sites/default/files/d8/2019-07/vertical-logo-monochromatic.png" /></div>

O Docker se trata de uma plataforma de desenvolvimento on podemos criar, executar e compartilhar aplicações dentro de containers. O uso de containers para fazer Deploy de aplicações se torna um processo bem mais simples quando utilizamos Docker. Tudo isso junto com a flexibilidade e portabilidade que um container docker nos trás é o bastante para tornar esta uma das ferramentas principais para desenvolvimento.

## Onde encontrar

O Docker ele poder ser encontrado em dois locais. Algumas distribuições linux nos permitem que adicionemos um repostiório apt do docker ao nosso sistema, no qual podemos instalar o docker via terminal. Para isso basta executar os passos abaixo:

#### Configurando repositório

1. Atualizaremos os pacotes `apt` e instalaremos alguns pacotes que permitem que o `apt` use repositórios via HTTPS

```
$ sudo apt-get update

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

2. Adicionamos a chave GPG oficial do Docker

```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

3. Verificamos se você possui a chave com a seguinte impressão `9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88`, pesquisando pelos seus últimos 8 dígitos.

```
$ sudo apt-key fingerprint 0EBFCD88

pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

4. Use o seguinte comando para adicionar o repositório estável

```
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

Detalhe: o `[arch=XXX]` é referente a arquitetura do seu sistema, verifique qual a sua e subistitua no comando se for necessário.
Arquiteturas mais comuns:

```
amd64 | armhf | arm64 | ppc64el | s390x
```

## Como instalar

Após adicionar o repositório devemos atualizar o pacote apt para que ele reconheca o repositório e possamos instalar o docker

```
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Caso ocorra um erro ao atualizar o pacote apt e o sistema não tenha reconhecido o repositório corretamente (O que pode ocorrer em algumas distros baseadas em ubuntu) não se preocupe, é possível baixar os arquivos .deb diretamente do <a href='https://download.docker.com/linux/ubuntu'>repositório</a>.

Você deverá procurar a distro na qual seu sistema é baseada e baixar os arquivos .deb das versões estáveis encontrados dentro da pool desta distro e que seja referente a sua arquitetura. Por exemplo

```
ubuntu/dists/bionic/pool/stable/amd64/
```

Lá você encontrará os arquivos .deb e poderá baixar e instalar a ultima versão do `docer-ce`, `docer-ce-cli` e `containerd.io`.

Executáveis .deb podem ser instalados com dois cliques, então é só esperar o processo de instalação finalizar; você também pode instalar com o seguinte comando `sudo dpkg -i nome_arquivo.deb` (deve ser executado na pasta onde está o arquivo).
