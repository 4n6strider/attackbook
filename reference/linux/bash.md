# BASH



```bash
# history 
CTL-R                       
history -c                 
space [command]   # hides from history 
history | grep [phrase]
 
#redirect errors to null
[command] 2>/dev/null

# redirect output and errors to null 
[command] > /dev/null 2>&1 

#wait for background jobs to complete 
wait $(jobs -p) 

#loop through a file
for [var] in $(cat [file]); do [command] $[var]; done
```

