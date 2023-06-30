# Configuracao-Roteador

# Ferramenta utilizada Cisco Packet Tracer

Para realizarmos a configuração dos equipamentos da Cisco, precisaremos utilizar um cabo especial: cabo console. Ele terá o seguinte formato:

<img src=https://github.com/xleofarias/Configuracao-Roteador/blob/master/Aula%2B6_3_cabo%2Bconsole.png>
Imagem do cabo Console</img>
<br></br>

- Descrição do cabo console:
  - Em que uma das pontas terá o conector plástico (RJ45) e na outra, terá o conector que recebe o nome de Rs232, referente a uma porta serial (que transmitirá os bits um por vez). A conexão real será feita com o RJ45 sendo conectado na porta de console do roteador e o Rs232 será conectado na porta do computador. No entanto, a maioria dos computadores fabricados atualmente não possuem está porta serial, elas foram substituídas pelo USB. Isto significa que precisaremos usar um adaptador para realizar a configuração do equipamento.

E que programa será usado para utilizar o equipamento da Cisco? Existem programas que chamamos de Terminal, o mais famoso deles se chama PuTTY e é bastante utilizado.

- O PuTTY é muito útil quando queremos acessar remotamente um equipamento. Isto significa que podemos acessar um equipamento em outra cidade e configurá-lo. Se tiver alguém na outra localidade que permita o acesso à distância, não precisaremos nos deslocar para realizar a configuração. Por isso, ele é bastante utilizado, além de ter um interface gráfica que não é tão cansativa.

Logo após os computadores estarem conectados via cabo crossover, também conhecido como cabo cruzado, é um cabo de rede par trançado que permite a ligação de 2 computadores pelas respectivas placas de rede sem a necessidade de um concentrador ou a ligação de modems. A ligação é feita com um cabo de par trançado onde tem-se: em uma ponta o padrão T568A, e, em outra, o padrão T568B. Ele é usado em um conector RJ-45.

No CLI do roteador iremos utilizar o comando ? que é o de ajuda, com ele podemos descobrir o comando para realizar a tarefa que precisamos.

- Passo 1
  -  Utilize o comando 'enable' para ativar o modo privilegiado, precisamos está com ele ativado para configurar o roteador com os PCs.
  -  Agora iremos utlizar novamente o ? para ver os novos comandos que foram liberados.
- Passo 2
  -  Utilize o comando 'configure terminal' assim entramos no modo de configurar o computador. Lembre-se estamos no sistema do roteador que queremos configurar.
  -  Assim começaremos a habilitar as portas. Habilitaremos a porta "FastEthernet 0/0", com o comando "Router(config)#interface fastEthernet 0/0". Com isso entramos no modo de configuração de interface.
  -  Para habilitá-la utilizamos o comando "no shutdown", com isso a porta está habilitada.
  -  Digite "exit" já que a porta foi ativada com sucesso.
  -  Realizar essa etapa com todas as portas que queira habilitar, irá apenas mudar o "FastEthernet 0/0" para "FastEthernet 0/1", "FastEthernet 0/2" por diante.
- Passo 3
  - Precisaremos ainda configurar o endereçamento IP que cada uma das portas receberá, para isso utilize o comando ip ? para receber um auxilio no processo.
  - Com o comando ip address podemos configurar o ip, tanto estático ou dinamico. Vamos configurar de forma estática. Assim ip address [ip da rede] mais a mascara de rede 255.255.255.0. Faça essa etapa para todas as maquinas.
- Passo 4
  - Até então os computadores não sabem fazer conexão com outros computadores de outra rede, para isso precisamos criar um default Gateway, assim ele irá enviar os pacotes para o roteador e de lá o roteador se vira para identifica qual ip terá que receber os pacotes.
  - Esse ip é o que configuramos um pouco antes, o ip da rede, ele precisa ta configurado no computador referente a FastEthernet correta.
  - Logo após isso os computadores já conseguem se comunicar.
