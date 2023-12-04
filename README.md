# dotfiles
Meus arquivos de configuração para o bash, GTK e outras aplicações.

## Importante!

Os arquivos na raiz do repositório devem ser copiados ou linkados para a raiz da pasta do usuário. Os arquivos e diretórios constantes no diretório **"config"** devem ser linkados para o subdiretório **".config"**, no diretório do usuário. Exemplos:

```sh
$ cp config/user-dirs.dirs ~/.config
$ cp dot-Xresources ~/.Xresources
$ ln -s dot-bashrc ~/.bashrc
$ ln -s dot-inputrc ~/.inputrc
$ ln -s config/autostart ~/.config
```

Linkar é mais fácil: uma vez atualizado o arquivo original, o link irá apontar para o mesmo, bastando, quando muito, reiniciar a sessão. Se você optar por copiar os arquivos, sempre que fizer alguma alteração deverá atualizar.

## xtras

No diretório **"xtras"** há um arquivo de entrada de desktop que permite a inicialização do gerenciador de janelas **DWM** a partir de gerenciadores de sessão como o **LightDM**. Este arquivo deverá ser copiado para o local apropriado usando permissões administrativas:

```sh
$ sudo cp xtras/dwm.desktop /usr/share/xsessions
```

Se o diretório ```/usr/share/xsessions``` não existir, será necessário criá-lo, também usando permissões administrativas:

```sh
$ sudo mkdir /usr/share/xsessions
```

Outro arquivo útil no diretório **"xtras"** é um script denominado **"dmenu_run_desktop"**. Este script permite que o lançador de aplicativos **dmenu** possa ler e apresentar os aplicativos que dispõem de arquivos de entrada de desktop no diretório ```/usr/share/applications```. Este script também precisa ser movimentado para um diretório específico, utilizando permissões administrativas:

```sh
$ sudo cp xtras/dmenu_run_desktop /usr/local/bin
```

Na minha versão patcheada do gerenciador de janelas **DWM**, os aplicativos são lançados pelo **dmenu** usando as teclas **WIN+P**, e já é usado o script acima por padrão. Para usar o dmenu da forma _"normal"_ (.i.e., lendo todos os arquivos alcançados pela variável ```$PATH```), é preciso utilizar a combinação **WIN+SHIFT+P** .
