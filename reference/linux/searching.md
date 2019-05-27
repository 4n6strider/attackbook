# Searching



```bash
#searches the path
which [file]  

#slower search but thorough
find / -name file\* 2>/dev/null
find / -iname *file* 2>/dev/null
find . -type f -name "*[file]" -exec cp {} [path] \;
find . -mtime 1               # 24 hours
find . -mtime -7 -type f      # files modified in last 7 days

#fast search uses local db
locate [file]
locate -i [file]
updatedb

grep
grep -r [string] .   #recursive
grep [string] [file] | cut -d [delimiter] -f [fields]
grep -v #invert match
grep -i #ignore case
grep -il [string] *.[files] #show matching filenames, case insensitive
grep -A [5]  # show five lines after the match
grep -B [5]  # show 5 lines before the match

echo "Here is a string" | grep -o -P '(?<=Here).*(?=string)'
echo "Here is a String" | grep -Po '(?<=(Here )).*(?= String)'

$ echo 'Here is a string, and Here is another string.' | grep -oP '(?<=Here).*(?=string)' # Greedy match
 is a string, and Here is another 
$ echo 'Here is a string, and Here is another string.' | grep -oP '(?<=Here).*?(?=string)' # Non-greedy match (Notice the '?' after '*' in .*)
 is a 
 is another 

$ echo "Here is a string" | awk -v FS="(Here|string)" '{print $2}'
 is a 

#everything between "one" and "two"
sed -e 's/one\(.*\)two/\1/'

sort -u

#get start or end of file
head [file]
tail [file]

# get all IP's from a log and sort by frequency
cat access.log | cut -d " " -f 1 | sort | uniq -c | sort -urn
```

