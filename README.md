
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

1) **get-imphash <file_path> -a <algorithm>** -> get-imphash c:\windows\system32\svchost.exe -a md5
2) **get-imphash * --algorithm <algorithm>**  -> get-imphash * -a sha256
3) **get-imphash --help**
4) **Algorithms supported:** SHA1, SHA256, SHA512, MD5.
