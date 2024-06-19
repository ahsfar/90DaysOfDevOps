## To view what's written in a file.
cat file_name

## To change the access permissions of files.
chmod 444 file_name

## To check which commands you have run till now.
history

## To remove a directory/ Folder.
rmdir dir_name

## To create a fruits.txt file and to view the content.
touch fruits.txt
cat fruits.txt

## Add content in devops.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.
cat devops.txt
content

## To Show only top three fruits from the file.
cat devops.txt | head -3

## To Show only bottom three fruits from the file.
cat devops.txt | tail -3

## To create another file Colors.txt and to view the content.
touch Colors.txt

## Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.
cat Colors.txt
content

## To find the difference between fruits.txt and Colors.txt file.
diff fruits.txt Colors.txt
