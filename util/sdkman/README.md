# SDKMAN

<div style="text-align:center"><img src="https://avatars.githubusercontent.com/u/2574205?s=200&v=4" /></div>

SDKMAN! é uma ferramenta para gerenciar versões paralelas de vários Software Development Kits(SDK). Ele fornece uma interface de linha de comando (CLI) e API convenientes para instalar, alternar, remover e listar candidatos. 

Imagine você instalando e gerenciando versões do Java, Maven, Gradle, Spring Boot, Groovy, Kotlin e muitos outros SDKs para a JVM numa única ferramenta, de maneira fácil e rápida. Legal né? 

## Como instalar

Para instalar o SDKMAN, abra o terminal e rode o seguinte comando: 

```
curl -s "https://get.sdkman.io" | bash
```
Siga as instruções na tela para concluir a instalação. À partir daí, você pode abrir um novo terminal ou rodar o seguinte comando:

```
source "$HOME/.sdkman/bin/sdkman-init.sh"
```

Com `sdk version` podemos verificar se a aplicação foi instalada com sucesso. Será retornado algo parecido com `sdkman 5.0.0+51`.

Agora você pode instalar, por exemplo, a última versão estável do Java:

``` sh
sdk install java ### sdk i java
```
Pode também instalar uma versão específica:

``` sh
sdk install java 11.0.13.8.1-amzn ### sdk i java 11.0.13.8.1-amzn
```
Se deseja listar todas as versões disponíveis rode:

``` sh
sdk list java ### sdk l java
```

Instale qualquer e quantas versões você desejar. Escolha facilmente qual será a versão atual do seu sistema:

``` sh
sdk use java 8.312.07.1-amzn ### sdk u java 8.312.07.1-amzn
```  


**Por fim:**
* Para mais detalhes de uso do SDKMAN acesse: https://sdkman.io/usage; 

* A instalação de todas as versões, de todos os SDKs ficam em `$HOME/.sdkman/candidates`. Numa IDE, você poderia apontar para uma versão do SDK que não é a atual do seu sistema;

* Em `$HOME/.sdkman/candidates/<sdkName>` você verá um atalho chamado `current` que aponta para a versão do SDK atualmente em uso.


