# NVM

<div style="text-align:center"><img src="https://miro.medium.com/max/1400/1*0HGTGpb0bdSo_xdlptb4-A.png" /></div>

O nvm trata-se de um gerenciador de versões do node.js. Ele é bastante útil quando se trabalha com diversos projetos em versões diferentes do node (e isso é bem comum), pois trabalhar com uma versão fixa pode causar alguns problemas (e isso é mais comum ainda).

## Onde Encontrar

O nvm e toda a sua documentação pode ser encontrada direto na sua <a src="https://github.com/nvm-sh/nvm">página</a> no github.

## Como instalar

É possível instalar o nvm por **curl** ou por **wget**. Escolha um dos dois comandos abaixo e rode no seu terminal.

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

```
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash

```

Após rodar algum desses comandos feche o terminal que você estava utilizando e abra outro usnado o comando a baixo para ver se o nvm foi instalado com sucesso

```
command -v nvm
```

o resultado deve ser uma mensagem com `nvm`. Caso ocorra algum erro, tente procurar por alguma alternativa na parte de instalação na documentação do nvm linkada anteriormente.

## Instalando a Node LTS

Após instalar o nvm, já podemos gerenciar nossas versões do node. Mesmo que você não possua nenhuma versão, podemos intalar a primeira aqui com o comando:

```
nvm install --lts
```

Isso vai instalar a ultima versão estável do node, e junto do node virá o npm, também na sua última versão estável.

Após isso, devemos indicar ao nvm que queremos utilizar esta versão, então usamos o comando:

```
nvm use --lts
```

E pronto, já temos a ultima versão do node instalada em nossa máquina. Para gerenciarmos outras versões os mesmo comandos serão utilziados, mas ao invés de `--lts`, você terá de indicar a versão que deseja utilizar.
