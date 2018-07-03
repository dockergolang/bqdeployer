# bqdeployer

## How to Setup?

First you will need to install docker, refer following link for the same:
[Docker Installation instructions for ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)

- Once done, you need to pull this image.
```
docker pull sanksons/bqdeployer:v1.1
```
- Now, add following ENV: (Modify username with your ssh user)
```
export SSH_USER={username}
```
- Make following alias in your ```~/.bash_aliases``` file:
```
alias release-box='docker run -it \
-v ${HOME}/.ssh:/root/.ssh \
-e SSH_USER=$SSH_USER \
--mount source=bqdep,target=/usr/local/boutiqaat sanksons/bqdeployer:v1.2'

```
- Now, run the command.
```
source ~/.bashrc
release-box
```
- Once inside the container, execute:
```
deployer
```
