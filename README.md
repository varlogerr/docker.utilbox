# docker.utilbox
```
mkdir -p ~/.my_bin && cd $_ \
  && git clone https://github.com/varlogerr/docker.utilbox.git \
  && cp -R ./docker.utilbox/tools/. ./ \
  && cat docker.utilbox/assets/.docker_utilbox_bashrc \
    | sed -e "s#{{ scripts_dir }}#$(pwd)#" \
    > ~/.docker_utilbox_bashrc \
  && echo "source $HOME/.docker_utilbox_bashrc" >> ~/.bashrc \
  && source ~/.bashrc
```
And you have following tools at your disposal:
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

Each tool automatically grabs `.env` file from pwd if it exists.  
Default node version with associated npm is `8.9.*` (i.e. latest LTS for the moment). If you want to change it just use an environment variable `NODEV`, just like that: `NODEV=6.9 node index.js` or add `NODEV=<desired-version>` to your `.bashrc` / `.bash_profile`.  
`DOCKUTILS_NODE_PARAMS` and `DOCKUTILS_COMPOSER_PARAMS` env variable will be passed to params string to `docker run` in addition to hardcoded ones.
