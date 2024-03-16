
# *Get-ImpHash* & *Get-Exphash* because *Get-FileHash* is lonely.

### This Project simply gives you a quicker way of getting the **Import Hash (IAT)** hash & the **Export Hash (EAT)** Hash from your PowerShell Instance.


#### To Implement This on your host, do the following steps:

1) Download the **impexp.txt** file.
   
2) Open PowerShell with **elevated permissions**.
   
3) **Execute the following:**
   Set-ExecutionPolicy RemoteSigned,
   Yes-to-all
  
4) **Execute the following:**
   Test-Path $PROFILE
   , If the output is **"True"**, skip **step 5**. If output is **"False"**, implement **step 5.**
   
5) **New-Item -Path $PROFILE -ItemType File -Force** (This will create a file called Microsoft.PowerShell_profile.ps1 in Documents folder)
   
6) **Execute the following:**
   notepad $PROFILE
   
7) **Paste** the code in the impexp Text File.

8) **Save, Close**.
    
9) **Congratulations**.

# Usage (pretty ez)
+ ### Get-ImpHash Command:

1) **get-ImpHash <file_path> -a <algorithm>**
   
   > get-ImpHash c:\windows\system32\svchost.exe -a md5
2) **get-ImpHash * --algorithm <algorithm>**
   
   > get-ImpHash * --algorithm sha256
3) **get-imphash --help**
4) **Algorithms supported:** SHA1, SHA256, SHA512, MD5.

+ ### Get-ExpHash Command:

1) **get-ExpHash <file_path> -a <algorithm>**
    
   > get-ExpHash c:\windows\system32\svchost.exe -a md5
2) **get-ExpHash * --algorithm <algorithm>**
   
   > get-ExpHash * --algorithm sha256
3) **get-ExpHash --help**
4) **Algorithms supported:** SHA1, SHA256, SHA512, MD5.
