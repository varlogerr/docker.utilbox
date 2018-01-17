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
