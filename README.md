# Instalando  o Virtual Guest Additions no Debian

<h3>
	<p>
Em Distribuiçoes Linux é possivel adicionar de uma forma  mais simplificada tais como:  Ubuntu, Xubuntu, Lubuntu, Linux Mint, Zorin entre outros.

 Porém no Debian é um pouco diferente o processo
</p>
</h3>
 <hr>

 ## Passo Realizados

```bash
 1  Atualizando pacotes e verificando a versão
    
    1.1   apt-get update # Atualizando
    1.2   lsb_release -a # Verificando a versão do S.O
```
```bash
2 Instalação  dos pacotes
    
    2.1   apt-get install module-assistant build-essential
    2.2   apt-get update, apt-get upgrade

    2.3 Preparando o ambiente 
          m-a prepare # faz a preparação do ambiente para o "instalador"
```
```bash
3 Verificando montagem da midia

    3.1   cd /media/cdrom # verificar se a midia está montada
    3.2   ls  # lista os arquivos

    3.3 No menu principal do VirtualBox # Inserindo Imagem de cd dos Adicionais para convidados
	 acessar Dispositivos -> selecionar a opção : Inserir Imagem de cd dos Adicionais para convidados

    3.4 no terminal novamente  verificar  se a midia foi montada com o comando  ls

    3.5 caso  não execute o comando:
          mount /media/cdrom

	# obs: será exibido a mensagem 
        # mount: /media/cdrom0: WRNING: source write-protected, mounted read-only
	    # Caso  não apareça refaça o procedimento (3.3)
```
```bash
4 Executando comandos
    
    4.1   cd - 
    4.2   cd /media/cdrom
    4.3   ls # É visualizado os  arquivos VBoxLinuxAdditions.run
    4.4   sh VBoxLinuxAdditions.run
    4.5 - Reinicie o sistema e teste o redimensionamento

```
```bash
5 Criação de pasta compartilhada (no Windows)

    5.1 - No menu do VirtualBox ir na Opção:
       Dispositivos -> Pastas Compartilhadas -> Configurações de Pastas Compartilhadas

       Clicar na pasta com sinal de + para adicionar -> Escolher o caminho,nome da pasta no Windows (Exemplo "C:\Usuarios\"Nome do usuário"\Desktop\Pasta") 

       
       # Observacao: No meu caso marquei a opção montar automaticamente 
```
      
```bash       
6 No terminal acessar como root:
    6.1   su / password

    6.2 digitar o comando  # verificar de a pasta é visualizada
          df

    6.2.1 - Já visualizo os  arquivos :
 	Filesystem ---1k---blocks--- Used--- Avaiable---Use%---Mounted on
	 /media/sf_TESTE/

```  
```bash
7.1 Para finalizar edite o arquivo txt criado na pasta compartilhada  (Windows) com as informações:

      linux 123456
      linux abcdef
      linux!@#$%¨&

    7.2 Acessando pasta compartilhada pelo terminal

    7.3 - No terminal acesse a pasta compartilhada:
          cd /media/sf_TESTE/

        Exibindo  o conteudo do arquivo de texto (output)

    7.4   cat arquivo-de-teste.txt # Onde podemos visualizar a informação do arquivo
```
```bash
8. caso não execute os seguintes passos/comandos:
    8.1    mkdir /mnt/teste 
    8.2    mount -t vboxsf "nome da pasta criada no compartilhamento - exemplo" TESTE /mnt/teste/
    8.3    ls /media/sf_TESTE/

    e posteriormente refazer  os passos  7.1 e 7.2

 ```


 [  Link do tutorial oficial ] (https://www.youtube.com/watch?v=m7slrh2OEec)
   ## Créditos para ( Ricardo Prudenciato )

