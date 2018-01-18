# docker.utilbox
Run
```
utilbox_bin_dir=$HOME/.dockerutil_bin; \
utilbox_bashrc_path=$HOME/.docker_utilbox_bashrc; \
mkdir -p $utilbox_bin_dir && cd $_ \
&& git clone https://github.com/varlogerr/docker.utilbox.git \
&& cp -R ./docker.utilbox/tools/. ./ \
&& cat docker.utilbox/assets/.docker_utilbox_bashrc \
  | sed -e "s#{{ scripts_dir }}#${utilbox_bin_dir}#" \
  > $utilbox_bashrc_path \
&& echo "source ${utilbox_bashrc_path}" >> $HOME/.bashrc \
&& source $HOME/.bashrc
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
`DNODE_PARAMS` and `DCOMPOSER_PARAMS` env variable will be passed to params string to `docker run` in addition to hardcoded ones. Same effect can be reached with files `.dcomposer_params` and `.dnode_params` in the pwd or / and HOME directory.  
Priority level (lowest to highest):  
* .d_params in HOME
* .d_params in pwd
* D_PARAMS env var
DNODE_PARAMS demo
```
DNODE_PARAMS="-p 3000:3000 -v $(pwd)/test:~/test"
```
.dnode_params demo
```
-p 3000:3000
-v $(pwd)/test:~/test
```
