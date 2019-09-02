# Commands of Linux

This is a note about Commands used in Linux

## Quick look
```bash
###### copy and move   ############

# copy directory and all its files
cp -avr [source] [destination]

# cp the files and subdirectory 
cp -v [source]/* [destination]

# move 
mv [source] [destination]

# remove file and directory
rm -r [folder]
rm *.txt

####### unzip and zip   ##########

unzip filename.zip -d /path/to/directory

# no print 
unzip -q filename.zip

# with a password
unzip -P PasswOrd filename.zip

# get information
unzip -l filename.zip

# unzip a.zip001,a.zip002...
cat file.zip* > file.zip
unzip file.zip

tar –xvf file.tar 

tar –xzf file.tar.gz

####### path     ##############

# return home path
cd ~

# show current path
pwd

# read txt
head [path]

```
