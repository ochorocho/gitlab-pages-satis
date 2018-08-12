# gitlab-pages-satis

## Generate Gitlab Config

```bash
vendor/bin/satis-gitlab gitlab-to-config --homepage https://satis.knallimall.org --output satis.json https://gitlab.example.org TOKEN
```

## Build Satis

```bash
vendor/bin/satis-gitlab build satis.json web
```

## Build all

```bash
bin/gitlab-pages-satis
```

### Specify config 

```bash
bin/gitlab-pages-satis /path/to/config.yml
```
 
### Using env variable

```bash
export GITLAB_SATIS_CONFIG="
arguments:
  gitlab-url: 'https://gitlab.example.org'
  gitlab-token: 'TOKEN'
options:
  homepage: 'https://satis.example.org'
  output: 'satis.json'
  ignore: '(^knallimall\/typo3-desktop)'
build-dir: './public'
  "
```

# Example config

```yaml
arguments:
  gitlab-url: 'https://gitlab.example.org'
  gitlab-token: 'TOKEN'
options:
  homepage: 'https://satis.example.org'
  output: 'satis.json'
  # Make sure string is escaped correctly
  ignore: '(^knallimall\/typo3-desktop)'
build-dir: './public'
```

# TODO

* Create `.htaccess` file and include in config
* Add to packagist
* Build Docker Image
* Run "on tag create"

# Features


* Config
  * Default: ./config.yml
  * env: GITLAB_SATIS_CONFIG
  * set config gitlab-pages-satis /path/to/config-file.yml
* All values of `options`-section are passed as `--option-key` to the command, so all satis/satis-gilab options are available
* All values of `arguments`-section are passed as `argument-key` to the command, so all satis/satis-gilab command arguments are available

# Development

* `git clone https://github.com/ochorocho/gitlab-pages-satis.git`
* `composer install`
* create config file, see config.example.yml
* run it `./bin/gitlab-pages-satis`