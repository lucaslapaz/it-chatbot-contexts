Tutorial de como instalar e configurar o OpenVPN


# Criação de usuário
Antes de tudo, para que seus usuários sejam criados e você tenha acesso às suas credenciais, abra um ticket via slack no canal no Slack(link do canal do slack: https://solfacil.slack.com/archives/C02EAGR061K) (como mostrado aqui (link de um vídeo onde mostra como abrir o ticket: https://solfacil.slack.com/archives/C02EAGR061K/p1663683452444869), caso necessário solicite ser adicionado no canal), então o time vai criar o seu usuário e enviar suas credenciais por DM. Após isso, pode seguir para os tutoriais! 

# Procedimento para conectar na VPN usando OpenVPN no Windows:

1. Acesse o site https://openvpn.net/downloads/openvpn-connect-v3-windows.msi para baixar o OpenVPN Client de acordo com seu sistema operacional;

2. Instale o OpenVPN Client e mantenha todas as opções padrões marcadas;

3. Depois de instalado, execute o OpenVPN em seu sistema operacional e em seguida aparecerá um ícone parecido com um imã na barra do windows, perto do relógio do sistema conforme print abaixo: (link da imagem ilustrativa do passo 3: https://i.imgur.com/6HOZdOk.png);

4. Dê dois cliques no ícone do OpenVPN para abrir e o mesmo aparecerá na tela. Em seguida selecione FILE e importe seu arquivo com extensão .ovpn para o OpenVPN conforme mostrado abaixo: (link da imagem ilustrativa do passo 4: https://i.imgur.com/UBz8pbm.png);

5. Após a importação do arquivo *.ovpn, clique em “Add” e conecte-se a VPN Solfacil.

**Como eu sei que a VPN já está funcionando?**
Simples. Acesse o seguinte site em seu navegador: https://httpbin.org/ip. Em seguida será exibido o IP da nossa VPN “3.220.149.180”.

# Procedimento para conectar na VPN usando OpenVPN no Linux (Ubunto):

Tutorial dispoível no site do OpeVPN para diversas distibuições linux: https://openvpn.net/cloud-docs/openvpn-3-client-for-linux/. Ou, para distribuições baseadas em Debian, rodar o comando abaixo e seguir os passos do tutorial do Ubuntu: 

``` bash
sudo apt-get install openvpn network-manager-openvpn network-manager-openvpn-gnome
```

# Procedimento para conectar na VPN usando OpenVPN no Mac:
Basta entrar no link: https://openvpn.net/client-connect-vpn-for-mac-os/ e baixar o client para Macbook. Depois importar o arquivo e adicionar a senha que lhe foi enviada no email pelo time de Devops.

# Erro de parâmtros no OpenVPN Client no Windows:
No windows após a última atualização do client lançado dia 10 Julho 2023 um dos parâmetros setados no arquivos .ovpn não é mais aceito causando o erro abaixo:
(imagem ilustrativa mostrando uma mensagem de erro onde diz: "Connection Failed. There was an error attempting to connect to the selected server. Error message: option_error: sorry, unsupported options present in configuration: UNKNOWN/UNSUPPORTED OPTIONS. Please refer to connection logs for more details": https://imgur.com/a/M7fMuuK).

Este erro ocorre por conta de um parâmetro existente no arquivo .ovpn que não é mais utilizado.

## Correção do problema de parâmetros no OpenVPN no Windows:

1. Primeiramente, será necessário remover a conexão existente. Clique em editar, como mostrado na imagem: (imagem ilustrativa onde mostra os perfís configurados e um ícone de lápis que está sendo apontado por uma flexa: https://i.imgur.com/0rkXBH1.png);

2. Na tela que abrir, clique em 'DELETE PROFILE' (imagem ilustrativa mostrando a tela de edição do perfil, tendo uma flecha apontada para o botão 'DELETE PROFILE': https://i.imgur.com/CDsyUWM.png);

3. Agora será necessário editar o arquivo '.ovpn'. Para isso, clique com o botão direito em cima do arquivo '.ovpn', vá em 'Abrir com' e selecione o 'Bloco de notas' (imagem ilustrativa mostrando como abrir o arquivo '.ovpn' com o bloco de notas: https://i.imgur.com/VlM5Z2W.png);

4. Procure e remova a linha com o parâmetro `tun-mtu-extra 32` (imagem ilustrativa apontando com uma flecha qual linha deve ser removida: https://i.imgur.com/fougwWt.png);

5. Feito isso, salvar (ctrl + s) o arquivo e sair.

6. Após isso, basta seguir com os passos iniciais de configuração mencionados no início deste tutorial.
