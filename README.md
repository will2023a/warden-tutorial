# warden-tutorial
ajuda na instalação e integração do warden com o banco de dados local

lembrando que precisa estar instalados o docker e docker compose

docker:
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt install docker-ce
sudo systemctl status docker

docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/v2.15.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version


instalação para windows 
brew install wardenenv/warden/warden
warden svc up

linux / mac

sudo mkdir /opt/warden
sudo chown $(whoami) /opt/warden
git clone -b main https://github.com/wardenenv/warden.git /opt/warden
echo 'export PATH="/opt/warden/bin:$PATH"' >> ~/.bashrc
PATH="/opt/warden/bin:$PATH"
warden svc up


depois disso para rodar o projeto colocar dentro de uma pasta src, entrar nela pelo terminal e rodar 
warden env-init
nome do projeto
nome da frame

depois

warden env up && warden svc up
warden shell entra dentro do warden.
prossiga com os comandos necessario da loja.


concentando db

![image](https://github.com/user-attachments/assets/14134b97-2965-4c5a-ad25-30b7cfe7683e)

na imagem acima, o server Host é o nome do container de db exibido pelo comando warden env ps.
a porta é a 3306 conforme aparece no container do comando acima.
para lojas magento a senha e usuario e database é magento.
após preencher essa parte principal vamos para aba ssh.

para Host/ip é  127.0.0.1 porta 2222
usr: user
Public key
caminho para a chave do warden na documentation esta path to ~/.warden/tunnel/ssh_key mas eu consegui assim
/home/<nomeusuariopc>/.warden/tunnel/ssh_key
passaphrase em branco e save credentials. 

