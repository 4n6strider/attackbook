# Git Client

Configure git globals

```bash
git config --global user.name "name"
git config --global user.email "email@"
git config --global color.ui true
git config --global core.editor nano
```

Generate an SSH key

```bash
ssh-keygen -t rsa -b 4096 -C "email@"

#copy the pub key to your git provider as an authorized SSH key
cat ./rsa_id.pub
```

Clone repository

```bash
#clone your repo
git clone user@url:/repository-name.git
```

