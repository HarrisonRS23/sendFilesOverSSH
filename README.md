# send files from local machine to server using ssh

# Setting up SSH Key

## first run this command on local host and press enter through prompts to use default values
ssh-keygen -t rsa
## ssh into server and create a ssh directory as intended user
ssh serverUsername@serverhost
mkdir -p .ssh
## copy public ssh key created on local machine onto server 
cat .ssh/id_rsa.pub | ssh b@B 'cat >> .ssh/authorized_keys'
## if this command is not working
copy contents of id_rsa.pub manually 
ssh into server
touch authorized_keys
paste copied contents into authorized keys

# Setting up secrets 
On github repository click settings -> secrets and variables -> actions -> new repository secret
1.) secret name: HOST ; secret value: ip address for server
2.) secret name: USERNAME ; secret value: username for server
3.) secret name: PORT ; secret value: port for server ( default 22) 
4.) secret name: KEY ; secret value: copy entire contents of id_rsa (including comments) from .ssh on local machine 
