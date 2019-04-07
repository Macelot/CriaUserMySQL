# CriaUserMySQL
Exemplo de script para criar usuários no MySQL

CREATE USER 'alunoDBA'@'%' IDENTIFIED BY '123456';

No comando acima estamos criando um usuário no MySQL com o nome alunoDBA e senha 123456
Perceba que este usuário por utilizar qualquer “%” computador(host) para logar no servidor, 
caso desejássemos limitar o acesso e exigir que o usuário apenas utilize um endereço(IP) específico, 
isso significa que o computador do usuário tenha o ip fixo:
CREATE USER 'alunoDBA'@'192.168.1.33' IDENTIFIED BY '123456';

Depois de criar o usuário é necessário definir as permissões destes nas bases desejadas.
O comando GRANT permite conceder privilégios aos usuários criados. 
Para permitir que o usuário tenha permissão em determinado banco de dados:

GRANT ALL ON frameWork.* TO 'alunoDBA'@'%';
flush privileges;

Perceba que estamos utilizando o flush privileges, este comando atualiza as permissões, pois alguns privilégios somente se 
tornam efetivos após a reinicialização do MySQL o do uso do flush privileges.

Perceba que o comando abaixo define permissões de usuário root!
GRANT ALL ON *.* TO 'alunoDBA'@'%';
flush privileges;

Isso é desaconselhável.	

O comando REVOKE permite retirar privilégios dos usuários criados. 
Para retirar todos os privilégios de um usuário.
REVOKE ALL ON *.* FROM 'alunoDBA'@'%';
flush privileges;

A única diferença (GRANT para REVOKE)  é que o TO vira FROM

Permissões mais específicas são possíveis:
GRANT select on framework.* to 'alunoDBA'@'%';
flush privileges;
