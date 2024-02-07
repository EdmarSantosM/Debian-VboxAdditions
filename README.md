# Debian-VBoxLinux

Instalando  o Virtual Guest Additions no Debian


Em Distribuiçoes Linux é possivel adicionar de uma forma  mais simplificada:
Ubuntu, Xubuntu, Lubuntu, Linux Mint, Zorin entre outros.

Porém no Debian é um pouco diferente o processo.

Para  que  está  estudando e fazendo labs e  curte o Debian é uma mão na roda, principalmente deixa em modo tela cheia, diga-se de passagem.

Observação  muito  já  vão direto  para o Ubuntu e suas ramificações 

Com ele é possível redimensionar  a tela,habilitar o compartilhamento (pasta, arquivos) entre host convidado e hospedeiro e vice versa.

Versão do Debian que instalei na VirtualBox : Debian 12

Passos realizados:

1-  Acessar o terminal e logar  como root
 1.1 - apt get update
 1.2 - lsb_release -a (Verificando a versão do S.O)  

2 - Instalação  do pacote
   2.1 - apt-get install module-assistant build-essential
   2.2 - apt-get update && apt-get upgrade.

    Após a finalização executar o comando abaixo
    m-a prepare ( faz a preparação do ambiente )  para o "instalador".

  3.1  acessar o cd /media/cdrom (verificar se midia está  montada)
  3.2 - ls
  3.3 - No menu principal do VirtualBox
	 acessar Dispositivos -> selecionar a opção : Inserir Imagem de cd dos Adicionais para convidados.

  3.4 no terminal novamente  verificar  se a midia foi montada com o comando  ls.
  3.5 caso  não execute o comando:
       mount /media/cdrom

	obs: será exibido a mensagem 
        mount: /media/cdrom0: WRNING: source write-protected, mounted read-only.
	Caso  não apareça refaça o procedimento (3.3)


   acessar novamente  com o comando cd /media/cdrom.
   * é visualizado os  arquivos (cd virtual).

 4.1 execute o comando  sh VBoxLinuxAdditions.run

 5.1 Reiniciar o sistema. (reboot)

 5.2 Testar o redimensionamento.

 5.3 Testa o compartilhamento de pasta:

 5.3.1 - No menu do VirtualBox ir na Opção:
       Dispositivos -> Pastas Compartilhadas -> Configurações de Pastas Compartilhadas...
       clicar na pasta com sinal de + para adicionar -> Escolher o caminho,nome da pasta no Windows ( Exemplo : C:\Usuarios\"Nome do usuário"\Desktop\Pasta.

       Obs: No meu caso marquei a opção montar automaticamente.

 6 No terminal acessar como root:
 6.1  -su / password

 6.2 digitar o comando df (verificar de a pasta é visualizada).


 6.2.1 - Já visualizo os  arquivos :
 	Filesystem -1k-blocks- Used- Avaiable-Use%-Mounted on
	 /media/sf_TESTE/

 7.1 Para finalizar editei o arquivo txt criado no windows com as informações:
  linux 123456
  linux abcdef
  linux!@#$%¨&

 7.2 - no terminal acessei a pasta compartilhada:
 7.2.1 - cd /media/sf_TESTE/
 7.2.2 - cat arquivo-de-teste.txt, onde consigo visualizar a informação




 8. caso não execute os seguintes passos/comandos:
   8.1 - mkdir /mnt/teste 
   8.2 - mount -t vboxsf "nome da pasta criada no compartilhamento - exemplo" TESTE /mnt/teste/
   8.3 - ls /media/sf_TESTE/

  e posteriormente refazer  os passos  7.1 e 7.2
       
