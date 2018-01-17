# docker.utilbox
```
mkdir -p ~/.my_bin && cd $_ \
  && git clone https://github.com/varlogerr/docker.utilbox.git \
  && cp -R ./docker.utilbox/_tools/. ./ \
  && cat docker.utilbox/_assets/.docker_utilbox_bashrc \
    | sed -e "s#{{ scripts_dir }}#$(pwd)#" \
    > ~/.docker_utilbox_bashrc \
  && echo "source $HOME/.docker_utilbox_bashrc" >> ~/.bashrc
```
Reload terminal and you have following tools at your disposal:
* composer
* phing
* phinx
* phpcpd
* phpmd
* phpunit
* nvm
* node
* npm
* bower
* gulp

Each of tool automatically grabs `.env` file from pwd if it exists.  
Default node version with associated npm is the latest one accessable from nvm. If you want to change it just use an environment variable `NODEV`, just like that: `NODEV=6.9 node index.js`
