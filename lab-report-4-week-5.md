# Charlotte Dong Lab Report4 (Week5)  
  
## find -s
* **find -s** --> *Cause find to traverse the file hierarchies in **lexicographical order**, i.e., alphabetical order within each directory.* This is especially helpful when we are given a bunch of files in random order, using **find -s** can help organize files in hierachy and lexicographical order, making it more organized and quicker for us to locate files.  
* **Example 1: find -s technical**  below is the code block and result of using **find -s** command on the entire technical folder. Notice that the results are nicely listed in alphabetical order. Because the terminal has limited space, I put the output into a file called **finds.txt**. This is helpful when we are given a directory that contains a lot of subdirectories and files, by using **find -s**, we can get a brief idea of the hierarchy and location of files under a specific subdirectory given the first letters of the file name.    
**command**  
```  
% find -s technical > finds.txt
```  
**output (won't include all file outputs since sapce is limited)**  
```  
technical
technical/911report
technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
... all files under technial/911report in alphabetical order ... 
technical/biomed
technical/biomed/1468-6708-3-1.txt
technical/biomed/1468-6708-3-10.txt
technical/biomed/1468-6708-3-3.txt
technical/biomed/1468-6708-3-4.txt
... all files under technial/biomed in alphabetical order ... 
technical/government
technical/government/About_LSC
technical/government/About_LSC/CONFIG_STANDARDS.txt
technical/government/About_LSC/Comments_on_semiannual.txt
... all files under technial/government/About_LSC in alphabetical order ... 
technical/government/Media
technical/government/Media/5_Legal_Groups.txt
technical/government/Media/AP_LawSchoolDebts.txt
technical/government/Media/A_Perk_of_Age.txt
... all files under technial/government/Media in alphabetical order ...
technical/plos
technical/plos/journal.pbio.0020001.txt
technical/plos/journal.pbio.0020010.txt
technical/plos/journal.pbio.0020012.txt
... all files under technial/plos in alphabetical order ...
```  
  
* **Example 2: find -s file1 file2 file3**  below is the code block and result of using **find -s** command on three files under technical. Notice that even though the 3 files on command line are in random order, **find -s** nicely organizes them in lexicographic (alphabetical) order in the output. Since we are expecting 3 lines of output, which does not take much space, I printed them directly in the terminal instead of putting them in a file. This is helpful when given some files and we need to get a brief idea of their hierachy and lexicpgraphic order compared to each other.  
**command**  
```  
% find -s technical/biomed/gb-2002-3-12-research0078.txt technical/911report/chapter-7.txt technical/biomed/1471-2148-1-4.txt
```  
**output**  
```  
technical/911report/chapter-7.txt
technical/biomed/1471-2148-1-4.txt
technical/biomed/gb-2002-3-12-research0078.txt  
```  
  
* **Example 3: find -s directory1 directory2**  below is the code block and result of using **find -s** command on two directories with * under technical. Notice that even though the 2 directories on command line are in random order, **find -s** expands to all files with directories of technical/plos/pmed.* and technical/911report/*, and organizes them in lexicographic (alphabetical) order in the output. This is helpful when given some directories and we want to find out their hierarchy and a list of all files under the given directory/subdirectory in alphabetical order.  
**command**  
```  
find -s technical/plos/pmed.* technical/911report/* > findsdifferenthierachies.txt
```  
**output (won't include all file outputs since sapce is limited)**  
``` 
technical/911report/chapter-1.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
technical/911report/chapter-12.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
... all files under technial/911report in alphabetical order ... 
technical/plos/pmed.0010008.txt
technical/plos/pmed.0010010.txt
technical/plos/pmed.0010013.txt
technical/plos/pmed.0010021.txt
technical/plos/pmed.0010022.txt
... all files under technial/plos with file name starting with pmed in alphabetical order ... 
```  
  
  
## find -name  
* **find -name** --> *True if the last component of the pathname being examined matches pattern. Special shell pattern matching characters (``['', ``]'', ``*'', and ``?'') may be used as part of pattern. These characters may be matched explicitly by escaping them with a backslash (``\'').* This is helpful when you know the pattern of file name that you want to search for, then this command will return all files that matches that pattern.  
* **Example 1: find technical/911report -name "*.txt"** This command finds and returns all files with name that matches the pattern *.txt. Because the pattern is in quotes, so not expanded, it looks for path *.txt in quotes. It is helpful when you know the directory and type of the file (shown in file name, in this case, .txt) and wants a list of all files with that pattern.  
**command**  
```  
% find technical/911report -name "*.txt"
```  
**output**  
``` 
technical/911report/chapter-13.4.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-13.1.txt
technical/911report/chapter-13.2.txt
technical/911report/chapter-13.3.txt
technical/911report/chapter-3.txt
technical/911report/chapter-2.txt
technical/911report/chapter-1.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```  
  
* **Example 2: % find technical/government/Media -name "Fund*.txt"** This command finds and returns all files under the directory **technical/government/Media** with file name that starts with **Fund**. This is helpful when you know the subdirectory of the file you want to find as well as a specific asepct you are interested in (in this case, fund), the command will give you a list of corresponding files.  
**command**  
```  
% find technical/government/Media -name "Fund*.txt"
```  
**output**  
``` 
technical/government/Media/Funding_cuts_force.txt
technical/government/Media/Funds_Shortage.txt
technical/government/Media/Funding_May_Limit.txt
```  
  
* **Example 3: % find technical -name og97050.txt** This command finds and returns the file with the exact name as you typed in. This is helpful when you are looking for a file with a specific name, but you don't know where exactly it is stored.  
**command**  
```  
find technical -name og97050.txt
```  
**output**  
``` 
technical/government/Gen_Account_Office/og97050.txt
```  
  
  
## find -size  
* **find -size** --> *True if the file's size, rounded up, in 512-byte blocks is n. If n is followed by a **c**, then the primary is true if the file's size is n bytes (characters).  Similarly if n is followed by a scale indicator then the file's size is compared to n scaled as:*
             k       kilobytes (1024 bytes)  
             M       megabytes (1024 kilobytes)  
             G       gigabytes (1024 megabytes)  
             T       terabytes (1024 gigabytes)  
             P       petabytes (1024 terabytes)  
This is helpful when you want to find files with certain size. Note that k, M, G, T, P are only useful for finding large-size files; since the file sizes under technical are fairly small, I won't demonstrate using find -size with k, M, G, T, P.  
  
* **Example 1: find technical/biomed/ -size 100** This commmand looks for files with size, rounded up, in 512-byte blocks is 100 inside the directory technical/biomed. This is helpful when you want to look for some files with certain size under a known directory.  
**command**  
```  
% find technical/biomed/ -size 100
```  
**output**  
``` 
technical/biomed//1471-2377-3-4.txt
technical/biomed//gb-2003-4-6-r39.txt
technical/biomed//gb-2003-4-3-r20.txt
```  
  
* **Example 2: find technical/government -size 10000c** This command looks for files whose size is 10000 bytes (characters) under the directory technical government. This is helpful when you know the general directory to filter and files with size of 10000 bytes (characters). If you know the specific size in byte of the files you want to find, add a **c** after n.  
**command**  
```  
% find technical/government -size 10000c
```  
**output**  
``` 
technical/government/Gen_Account_Office/og97052.txt
```  
  
* **Example 3: % find * -size 15** This command looks for files whose size, rounded up in 512-byte blocks is 15 under the technical directory. This is helpful when you want to filter and find files with specific size under the current directory.  
**command**  
```  
% find * -size 15
```  
**output**  
``` 
technical/government/Gen_Account_Office/og97045.txt
technical/government/Gen_Account_Office/og97046.txt
technical/government/Media/Legal_system_fails_poor.txt
technical/government/Media/BergenCountyRecord.txt
technical/government/Media/Avoids_Budget_Cut.txt
technical/government/Media/Greedy_Generous.txt
technical/plos/journal.pbio.0020147.txt
technical/plos/journal.pbio.0020040.txt
technical/plos/journal.pbio.0020262.txt
technical/plos/pmed.0010041.txt
technical/plos/journal.pbio.0020112.txt
technical/plos/journal.pbio.0020105.txt
```  
  
  




