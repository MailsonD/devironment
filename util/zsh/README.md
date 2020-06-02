# ZSH

<div style="text-align:center"><img src="https://ohmyz.sh/img/OMZLogo_BnW.png" /></div>

O zsh se trata de um shell para interpretar comandos UNIX. Mas o que de fato faz dele interessante é a sua flexibilidade quanto a customização e aos diversos plugins possíveis de se instalar nele, para melhorar sua experiência de uso.

## Como instalar

O Zsh é facilmente instalado através de pacotes binários. Em caso de sistemas baseados em Debian, como Ubuntu e o Mint, basta rodar o seguinte comando:

```
sudo apt install zsh
```

Após a conclusão, podemos verificar se o zsh foi instalado com sucesso utilizando o comando:

```
zsh --version
```

Este comando deve nos retornar a última versão estável do zsh, algo tipo `zsh 5.4.2`. Após isso podemos fazer do zsh nosso shell padrão através do comando:

```
chsh -s $(which zsh)
```

Após este comando, o zsh já deve ter sido definido como seu shell padrão. Para poder testar isso reinicie seu computador e abra um novo terminal para ver se tudo funcionou perfeitamente.

Após isso, poderemos rodar um `echo $SHELL` para verificar e garantir que o zsh foi instalado com sucesso. O resultado deve ser algo tipo `/bin/zsh`.

## Oh My Zsh

O Oh My Zsh é um "delicioso" (como dito no site oficial) framework de código aberto para gerenciar as configurações do Zsh. É através dele que você poderá instalar de maneira simples, temas, plugins e muitas outras coisas (como uma extensão para citar frases aleatórias do Chuck Norris). Além disso, ele tráz consigo diversas funcionalidades que facilitam a sua vida.

## Como Instalar

Para instalar o zsh, basta escolher entre a execução de um comando **curl** ou **wget** mostrados abaixo.

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

```

```
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

```

Após esta execução, você já notará a diferença que o Oh My Zsh fez ao seu Shell.

## Temas

O Oh My Zsh disponiliza inúmeros temas para que vc possa personalizar o seu terminal da maneira que mais te agrade. Os temas podem ser encontrados <a href='https://github.com/ohmyzsh/ohmyzsh/wiki/Themes'>aqui</a>, além de um tutorial rápido de como instalá-los.

## Plugins

O Oh My Zsh também disponibiliza um conjunto de plugins com inúmeras funcionalidades para tea ajudar nas horas de desenvolvimento.

Para instalá-los, basta escolher o plugin que vc quer instalar <a href='https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins'>aqui</a>, clonar seu repositório e adicioná-lo a pasta `~/.oh-my-zsh/custom/plugins`.

Após isso, basta habilitá-lo no seu terminal editando o arquivo `~/.zshrc` e adicionando o nome do seu plugin ao array de plugins.

Eu recomendo dois plugins que eu gosto de utilizar, são eles:

<ul>
    <li><a href='https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md'>zsh-autosuggestions</a></i>
    <li><a href='https://github.com/zdharma/fast-syntax-highlighting#installation'>fast-syntax-highlighting</a></i>
</ul>

E agora basta se divertir com o seu novo terminal customizado.
