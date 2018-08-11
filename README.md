# gitlab-pages-satis


## Generate Gitlab Config

```
bin/satis-gitlab gitlab-to-config --homepage https://satis.knallimall.org --output satis.json https://gitlab.example.org TOKEN
```


## Build Satis

```bash
bin/satis-gitlab build satis.json web
```