# Greetings!

## Exploring the `find` command
Today we will explore the `find` command, and its several use cases. The `find` command is a tool used for searching files or directories within a given directory or its subdirectories. Although it is quite simple, we can do many special things with this command, improving our quality of life.

---
### Option 1: `-name`
The `-name` option allows us to search for files based off their file name.

**Example 1:**
Input:
```bash
find ./technical -name "rr*.txt"
```
This command searches for all files that start with "rr" and end with ".txt" within `./technical` directory and its subdirectories. 

Output: 
```bash
./technical/biomed/rr166.txt
./technical/biomed/rr167.txt
./technical/biomed/rr171.txt
./technical/biomed/rr172.txt
./technical/biomed/rr191.txt
./technical/biomed/rr196.txt
./technical/biomed/rr37.txt
./technical/biomed/rr73.txt
./technical/biomed/rr74.txt
```

**Example 2:**
Input:
```bash
find ./technical -name "og*"
```
This command searches for all files that start with "og" and end with ".txt" within `./technical` directory and its subdirectories. 

Output:
```bash
./technical/government/Gen_Account_Office/og96009.txt
./technical/government/Gen_Account_Office/og96011.txt
./technical/government/Gen_Account_Office/og96012.txt
./technical/government/Gen_Account_Office/og96014.txt
./technical/government/Gen_Account_Office/og96015.txt
./technical/government/Gen_Account_Office/og96020.txt
./technical/government/Gen_Account_Office/og96021.txt
./technical/government/Gen_Account_Office/og96022.txt
./technical/government/Gen_Account_Office/og96023.txt
./technical/government/Gen_Account_Office/og96026.txt
./technical/government/Gen_Account_Office/og96027.txt
./technical/government/Gen_Account_Office/og96028.txt
./technical/government/Gen_Account_Office/og96031.txt
./technical/government/Gen_Account_Office/og96032.txt
./technical/government/Gen_Account_Office/og96033.txt
./technical/government/Gen_Account_Office/og96034.txt
./technical/government/Gen_Account_Office/og96036.txt
./technical/government/Gen_Account_Office/og96037.txt
./technical/government/Gen_Account_Office/og96038.txt
./technical/government/Gen_Account_Office/og96040.txt
./technical/government/Gen_Account_Office/og96041.txt
./technical/government/Gen_Account_Office/og96042.txt
./technical/government/Gen_Account_Office/og96043.txt
./technical/government/Gen_Account_Office/og96045.txt
./technical/government/Gen_Account_Office/og96047.txt
./technical/government/Gen_Account_Office/og97001.txt
./technical/government/Gen_Account_Office/og97002.txt
./technical/government/Gen_Account_Office/og97003.txt
./technical/government/Gen_Account_Office/og97011.txt
./technical/government/Gen_Account_Office/og97019.txt
./technical/government/Gen_Account_Office/og97020.txt
./technical/government/Gen_Account_Office/og97023.txt
./technical/government/Gen_Account_Office/og97028.txt
./technical/government/Gen_Account_Office/og97032.txt
./technical/government/Gen_Account_Office/og97038.txt
./technical/government/Gen_Account_Office/og97039.txt
./technical/government/Gen_Account_Office/og97041.txt
./technical/government/Gen_Account_Office/og97043.txt
./technical/government/Gen_Account_Office/og97045.txt
./technical/government/Gen_Account_Office/og97046.txt
./technical/government/Gen_Account_Office/og97050.txt
./technical/government/Gen_Account_Office/og97051.txt
./technical/government/Gen_Account_Office/og97052.txt
./technical/government/Gen_Account_Office/og98018.txt
./technical/government/Gen_Account_Office/og98019.txt
./technical/government/Gen_Account_Office/og98022.txt
./technical/government/Gen_Account_Office/og98024.txt
./technical/government/Gen_Account_Office/og98026.txt
./technical/government/Gen_Account_Office/og98029.txt
./technical/government/Gen_Account_Office/og98030.txt
./technical/government/Gen_Account_Office/og98032.txt
./technical/government/Gen_Account_Office/og98040.txt
./technical/government/Gen_Account_Office/og98041.txt
./technical/government/Gen_Account_Office/og98044.txt
./technical/government/Gen_Account_Office/og98045.txt
./technical/government/Gen_Account_Office/og98046.txt
./technical/government/Gen_Account_Office/og99036.txt
```
Overall, the -name command is great in finding specific files that are needed, and can help specify certain groups of subjects, whether its political, medical, etc.
To find more details about this option, visit [find command -name option](https://www.ionos.com/digitalguide/server/configuration/linux-find-command/)

---
### Option 2: `-size`
The `-size` option allows searching for files based on their size.

**Example 1:**
Input:
```bash
find ./technical -size +400b
```
This command searches for all files within the `./technical` directory and its subdirectories that are larger than 400 512-byte blocks. The `+400b` parameter specifies the size criterion.

Output: 
```bash
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical/government/Gen_Account_Office/d01591sp.txt
```

**Example 2:**
Input:
```bash
find ./technical -size -1000c
```
This command searches for all files within the `./technical` directory and its subdirectories that are smaller than 1000 bytes. The `-1000c` parameter specifies the size criterion.

Output: 
```bash
./technical/plos/pmed.0020191.txt
./technical/plos/pmed.0020226.txt
```

Overall, the -size command is great in filtering out different sizes of files, and can help you find the smallest/largest files within the directory. 
To find more details about this option, visit [find command -size option](https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size)

---
### Option 3: `-type`
The `-type` option allows us to search based on file type

**Example 1:**
Input:
```bash
find ./technical -type f | head -n 10
```
This command searches for all normal files within the `./technical` directory and its subdirectories. The `-type f` option filters the search to only include regular files. HOWEVER, for the sake of the assignment, using the piping method of only requesting the first 10 files instead of ALL the ".txt" files was done. 

Output: 
```bash
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
```

**Example 2:**
Input:
```bash
find ./technical -type d
```
This command searches for all directories within the `./technical` directory and its subdirectories. The `-type d` option filters the search to only include directories.

Output: 
```bash
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
Overall, the -type command is great in sorting the different types of file, directories, etc. We can focus on certain types without worrying about other types being involved.  
To find more details about this option, visit [find command -type option](https://www.ionos.com/digitalguide/server/configuration/linux-find-command/)

---
### Option 4: `-exec`
The `-exec` option allows us to include an extra command after using `-find`. It essentially makes a two liner a one liner. 

**Example 1:**
Input:
```bash
find ./technical -name "pmed.0020191.txt" -exec cat {} \;
```
This command searches for all files that have the name pmed.0020191" within `./technical` directory and its subdirectories. It then executes the `cat` command on each found file, displaying them , `{}` being their placeholder.

Output: 
```bash
  
    
      
        
        The excellent article by Jordan Paradise, Lori B. Andrews, and colleagues, “Ethics.
        Constructing Ethical Guidelines for Biohistory” [1], neither advocates nor argues against
        biohistorical research; instead, it points out that such investigations are currently
        taking place without guidelines—ethical, scientific, moral, or religious. The question
        remains: if such guidelines were to be established, what individuals, institutions,
        governments, medical examiners, family members, or intrepid biographers are to be given
        permission? Who is to decide what is “historically significant”? Not to mention the
        meta-question: who is to decide who is to decide? I apologize to the authors if my brief
        comments [2] implied that they took a position on this issue.
      

```

**Example 2:**
Input:
```bash
find ./technical -type f -exec rm {} \;
```
This command searches for all normal files within the `./technical` directory and its subdirectories. It then executes the `rm` command on each found file, removing them , `{}` being their placeholder.

Output: 
```bash


```
(After the code was executed, all subdirectories within `./technical` had their files deleted, and left blank. Using the `-ls` command on each of 911report, biomed, government, and plos, they had no ".txt" files stored in them)

Overall, the -exec command is great in not only finding certain files, types, etc, but it also includes an extra action do be done, simplifying longer lines of code. It is great for deleting everything, if that is what is desired. 
To find more details about this option, visit [find command -exec option](https://www.baeldung.com/linux/find-exec-command)
