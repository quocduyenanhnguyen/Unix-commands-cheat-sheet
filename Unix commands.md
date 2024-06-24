### 1. Print working directory
```Pwd```

### 2. Change working directory
```
Cd /pathname you want to move to
Ex: Cd /Applications
```

### 3. Move file(s) and directory to new directory
```
Mv filename (or directory name) /pathname
Ex: mv /Users/annanguyen/Downloads/Avatar.jpg /Users/annanguyen/Documents/Job_materials
```

### 4. Create new directory 
```
Mkdir /pathname
Ex: mkdir /Users/annanguyen/Documents/Anna_test
```

### 5. Delete directory
```
Rmdir /pathname
Ex: Rmdir /Users/annanguyen/Documents/Anna_test
```

### 6. Delete file
```
Rm /filename 
Ex: rm /Users/annanguyen/Documents/Test1.xlsx
```

### 7. Delete multiple directories or files
#### Delete Excel files contain either test1 or test2: 
```find /Users/annanguyen/Documents -type f \( -iname "*test1*.xlsx" -o -iname "*test2*.xlsx" \) -delete```
#### Delete directories contain either test1 or test2: 
```find /Users/annanguyen/Documents -type d \( -iname "*test1*" -o -iname "*test2*" \) -delete```

### 8. Find empty files or directories and delete them
```
find {dir-to-search} -type d -empty -delete
find {dir-to-search} -type f -empty -delete
Ex: 
find /Users/annanguyen/Documents -type d -empty -delete
find /Users/annanguyen/Documents -type f -empty -delete
```

### 9. Find files within specified time interval
#### Less than 3 days old: 
```find /Users/annanguyen/Documents -type f -mtime -3```
#### Within a date range: 
```find /Users/annanguyen/Documents -type f -newermt 20240620 \! -newermt 20240621```
#### 6 months ago: 
```find /Users/annanguyen/Documents -type f -newermt '6 months ago' \! -newermt 'today'```

### 10. Create a folder dynamically (I did this on Windows system)
```mkdir archived_PA_"$(date -d "6 months ago - 1 day" +%Y-%m-%d)"_"$(date -d "1 day ago" +%Y-%m-%d)"```

### 11. Move files to new folder dynamically (I did this on Windows system)
```find ./VA -newermt $(date +%Y%m%d -d '6 months ago') ! -newermt $(date +%Y%m%d -d 'today') -exec mv -t /var/log/pentaho/archived_PA_"$(date -d "6 months ago - 1 day" +%Y-%m-%d)"_"$(date -d "1 day ago" +%Y-%m-%d)" {} +```

### 12. Archive dynamic folder (I did this on Windows system)
```zip -r archived_PA_"$(date -d "6 months ago - 1 day" +%Y-%m-%d)"_"$(date -d "1 day ago" +%Y-%m-%d)".zip /var/log/pentaho/archived_PA_"$(date -d "6 months ago - 1 day" +%Y-%m-%d)"_"$(date -d "1 day ago" +%Y-%m-%d)"```

### 13. Find files or directory with regex 
#### Find files or directories contain ‘anna’: 
```
Find /Users/annanguyen/Documents -type d -iname "*anna*"
Find /Users/annanguyen/Documents -type f -iname "*anna*"
```
#### Find files based on file extension:
```Find /Users/annanguyen/Documents -type f -iname "*.pdf"```
#### Find files based on filename and file extension (i.e. PDF files contain ‘anna’):
```Find /Users/annanguyen/Documents -type f -iname "*anna*.pdf"```
#### Find files based on filename and file extension (i.e. PDF files contain ‘anna’) created 6 days ago:
```Find /Users/annanguyen/Documents -type f -iname "*anna*.pdf" -newermt '6 days ago'```

### 14. Find logs
#### Find system logs: 
```Find /private/var/log -iname "*system*.log"```
#### Find all logs: 
```Find /private/var/log -iname "*.log"```
#### Find logs contain words “errors”: 
```Find /private/var/log -iname "*error*.log"```

### 15. Create new files 
```Touch /Users/annanguyen/Documents/test.pdf /Users/annanguyen/Documents/test2.pdf /Users/annanguyen/Documents/test3.pdf```

### 16. View a file
```
Cat /Users/annanguyen/Documents/To_do_list.xlsx
More /Users/annanguyen/Documents/To_do_list.xlsx
Less /Users/annanguyen/Documents/To_do_list.xlsx
```
### 17. Find out file type
```File /Users/annanguyen/Documents/To_do_list.xlsx /Users/annanguyen/Documents/Job_materials/Resume_copy.pdf```

### 18. Copy file contents
```Cat /Users/annanguyen/Documents/To_do_list.xlsx > /Users/annanguyen/Documents/To_do_list.csv```

### 19. Concatenate files
```Cat /Users/annanguyen/Documents/To_do_list.xlsx /Users/annanguyen/Documents/To_do_list.csv > /Users/annanguyen/Documents/addon.xlsx```

### 20. Concatenate files and append
```Cat /Users/annanguyen/Documents/To_do_list.xlsx /Users/annanguyen/Documents/To_do_list.csv >> /Users/annanguyen/Documents/addon.xlsx```

### 21. Vi commands (I mainly use on crontab)
```Crontab -e, then type I to enter Edit mode (I stand for Insert). When finished, press ESC :wq to save changes.```

### 22. Rename file
```Mv /Users/annanguyen/Documents/To_do_list.xlsx /Users/annanguyen/Documents/Anna_To_do_list.xlsx```




