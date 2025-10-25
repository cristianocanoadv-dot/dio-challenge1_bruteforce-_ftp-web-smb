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
