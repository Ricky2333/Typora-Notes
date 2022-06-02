<center>
  <h1>
  		Linux Tutorial
  </h1>
</center>

## Basic Command Line

- ### Directory

```bash
pwd									#print work directory
ls									#list files
cd folder_path			#enter folder_path
cd .. 							#back to previous folder
cd ~    						#back to Home directory
exit								#exit bash
```

- ### Folder

```bash
mkdir new_folder		#create new_folder in work directory

rm -ri folder_name	#remove folder with interaction
rm -rf folder_name	#remove folder without interaction
rmdir empty_folder	#remove empty_folder(not recommended)
```

- ### File

```bash
touch new.txt 						#create new.txt in work directory

echo "hello" > new.txt		#create new.txt with content "hello"
echo "world" >> new.txt	  #append "world" to new.txt

cat test.txt							#show the content of test.txt

cat > test.txt            #create test.txt with new_content
new_content
⌃+D
cat >> test.txt           #append new content to test.txt
new_content
⌃+D

vi test.txt								#open "vi" to modify test.txt
vim test.txt							#open "vim" to modify test.txt
```

