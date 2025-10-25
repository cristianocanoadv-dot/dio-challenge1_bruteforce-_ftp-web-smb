(BR) 
# Desafio DIO 1 - Testes de invasão no Kali Linux

Este repositório guarda os arquivos e prints dos **3 desafios** que eu fiz no Kali Linux por brute force:
- Invasão FTP  
- Invasão DVWA (web)  
- Invasão SMB

## Ferramentas usadas: VirtualBox, KaliLinux

## Informações importantes
- O "usuário" se trata do metasploitable2 uma VM intencionalmente vulnerável criada para treinamento e testes
- As evidências (prints) estão na pasta `images/`  
- O histórico de comandos do terminal está salvo em `results/terminal_history.txt`
- Os testes foram feitos a partir da informação do número de IP do usuário (o qual tinhámos informação)
- Utilizei um ambiente controlado dentro do Virtual Box
- Este repositório foi criado apenas para **estudo e aprendizado**, sem fins maliciosos
  
## Invasão FTP
- Dei um comando Ping no terminal para o IP para testar a conexão com a máquina do usuário
- Utilizei o Nmap com os números das principais portas para ftp, ssh, http, smb, com o parâmetro "sV" que tenta identificar a versão do serviço de cada porta
- Em seguida, testando a opção ftp para o IP do usuário, tive uma resposta positiva, porta aberta e feita a conexão com login e senha (os quais ainda não sei)
- Crie duas wordlists para usuário e senha para combinações mais comuns User, nmsfadmin, nadmin, nroot, para senhas 123456, password, npassword etc. (comandos na pasta -> terminal_history.txt)
- Utilizei o Medusa e ele encontrou a combinação de usuário e senha para o terminal
- Testei e estava correto, invasão com sucesso.

## Invasão WEB
- Criei wordslists novamente para senhas e usuários possíveis
- Utilizei o Medusa para criar combinações de senhas e usuários
- Retornaram credenciais válidas, invasão com sucesso.

## Invasão SMB + Spraying 
- Comando Enum4linux
- Comando Less para navegar no comando e ter acesso ao arquivo
- Criei wordslists novamente para senhas e usuários possíveis
- Utilizei o Medusa para criar combinações de senhas e usuários
- Retornaram credenciais válidas, invasão com sucesso testada no terminal smbclient.

  (GB)
  # DIO Challenge 1 - Attack tests on Kali Linux

This repository stores the files and screenshots of the 3 challenges I performed on Kali Linux using brute force:
- FTP attack
- DVWA (web) attack
- SMB attack

## Tools used: VirtualBox, Kali Linux

## Important information
- The "user" refers to Metasploitable2, an intentionally vulnerable VM created for training and testing.
- Evidence (screenshots) is in the images/ folder.
- The terminal command history is saved in results/terminal_history.txt.
- The tests were performed based on knowledge of the target VM's IP address (which we had).
- I used a controlled environment inside VirtualBox.
- This repository was created only for study and learning purposes, with no malicious intent.
  
## FTP attack
- I ran a ping command to the IP to test connectivity to the target machine.
- I used nmap targeting the main ports for ftp, ssh, http, smb, with the -sV option to try to identify the service version for each port.
- Then I tested FTP connectivity to the target IP and got a positive response: the port was open and a connection was possible (credentials not yet known at that moment).
- I created two wordlists for users and passwords with common combinations (example users: user, msfadmin, nadmin, nroot; example passwords: 123456, password, npassword, etc.). (commands are in results/terminal_history.txt)
- I used Medusa and it found a valid username/password combination for the terminal.
- I tested the credentials and they were correct — attack successful.

## WEB attack
- I created wordlists again for possible usernames and passwords.
- I used Medusa to try username/password combinations against the web form.
- Valid credentials were returned — attack successful.

## SMB attack + spraying
- Ran enum4linux.
- Used less to inspect command output and access files.
- Created wordlists again for possible usernames and passwords.
- Used Medusa to try username/password combinations (password spraying).
- Valid credentials were returned — verified successfully in the terminal with smbclient.
