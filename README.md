# CriaUserMySQL
Exemplo de script para criar usuários no MySQL

CREATE USER 'alunoDBA'@'%' IDENTIFIED BY '123456';

No comando acima estamos criando um usuário no MySQL com o nome alunoDBA e senha 123456
Perceba que este usuário por utilizar qualquer “%” computador(host) para logar no servidor, 
caso desejássemos limitar o acesso e exigir que o usuário apenas utilize um endereço(IP) específico, 
isso significa que o computador do usuário tenha o ip fixo:
CREATE USER 'alunoDBA'@'192.168.1.33' IDENTIFIED BY '123456';
