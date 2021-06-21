# Drive_Install_Environment_Linux


Instalar o driver da placa de vídeo Sis 671/771 no Linux Mint 11


suporte às placas SiS Mirage 3 (771/761) no Linux, os chipsets da SiS, além de desempenho e qualidade ruins, são conhecidos pelo fraco suporte no Linux. O seu chipset de vídeo é o SiS Mirage 3 que é bem comum em notebooks de baixo preço.
linux-mint-11

Linux Mint 11

 funciona essa placa de vídeo com resolução de até 1280 x 768 no Linux Mint 11.

O Linux Mint, distribuição Irlandesa que tem versões baseadas no Ubuntu e no Debian. Nos últimos meses, tem sido a versão mais visitada no site DistroWatch.com, batendo o Fedora e o Ubuntu. É um Linux com melhor “acabamento” que os mencionados, mais fácil de mexer e configurar. E essa é exatamente a proposta da equipe de desenvolvimento, que propõe uma versão “out-of-the-box”, ou seja, pronta para usar assim que acabar a instalação.
Notebook
 

1º Fazer download dos drivers da placa:

Driver Winischhofer 32bits XServer 1.7

O arquivo baixado está compactado no formato TAR.GZ e você poderá descompactá-lo em qualquer lugar. Normalmente, ele será baixado para a pasta Downloads, dentro da sua pasta de usuário. Você pode descompactá-lo lá mesmo. Clique com o botão direito do mouse sobre o arquivo TAR.GZ e depois em Extrair aqui. Uma pasta 32-bits vai aparecer com 3 arquivos dentro:

    Readme.txt
    sis671_drv.la
    sis671_drv.so

Copie os arquivo sis671_drv.la e sis671_drv.so para a pasta /usr/lib/xorg/modules/drivers

    Abra o Terminal
    entre na pasta Downloads e depois em 32-bits (ou no local onde você descompactou o arquivo TAR.GZ)
    Digite sudo cp sis671_drv.* /usr/lib/xorg/modules/drivers
    Informe a senha do usuário root (super usuário)

Esse comando irá copiar (cp) os arquivos sis671_drv (o * significa qualquer extensão, tanto .la quanto .so serão copiados) para a pasta informada.

2º Fazer download do arquivo xorg.conf

É o arquivo responsável por utilizar os drivers copiados anteriormente. Não é preciso alterar nada no arquivo, simplesmente baixar e copiar na pasta correta.

Clique para fazer o download: xorg.conf (caso o download não seja efetuado, clique com o botão direito sobre o link e depois em Salvar Link Como)

Esse arquivo precisa ser copiado para a pasta /etc/X11. É interessante, primeiramente, fazer um backup do arquivo xorg.conf atual, ou seja, que já está na pasta /etc/X11 (caso ele exista).

Para efetuar o backup, no Terminal digite:

sudo cp /etc/X11/xorg.conf /etc/X11/xorg.old

Fazendo isso, o arquivo atual será copiado com o nome de xorg.old no mesmo local. Se caso ocorrer algum problema depois da configuração, volte esse arquivo para xorg.conf, executando o comando abaixo, também no Terminal:

sudo cp /etc/X11/xorg.old /etc/X11/xorg.conf

Agora, copie o xorg.conf que você acabou de fazer o download para a pasta /etc/X11:

sudo cp xorg.conf /etc/X11

Um detalhe: para o comando funcionar, você já precisa estar na mesma pasta onde gravou o arquivo xorg.conf.

3º Ferramenta de controle de configuração da placa no linux

Obs.: Esse passo é opcional e seu Linux já deveria estar com a resolução de 1280 x 768.

Faça o download do arquivo sisctrl_32

 depois de efetuar o download, basta clicar 2x sobre o mesmo para iniciar a instalação. O instalador de pacotes vai abrir bastando apenas que você clique no botão Instalar Pacote.

reiniciar o seu computador.

Utilizei como referência os endereços abaixo:

http://diversosassuntosbrasil.blogspot.com/2010/06/sis-671-672-mirage-3-funcionando-no.html
