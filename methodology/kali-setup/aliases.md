# Aliases

### ls

```text
echo "alias ll='ls -lvhAF --file-type --group-directories-first'" >> ~/.bash_aliases
echo "alias lr='ll -R'" >> ~/.bash_aliases
echo "alias ld='ll -tr'" >> ~/.bash_aliases
echo "alias lc='ll -tcr'" >> ~/.bash_aliases

source ~/.bash_aliases
```



