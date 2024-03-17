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

# Usage
+ ### Get-ImpHash Command:

1) **Get-ImpHash <file_path> -algorithm <algorithm> -ShowTable -delimiter 'delimiter'**
   
   > Get-ImpHash c:\windows\system32\svchost.exe -a sha256 -ShowTable -d ' | '
2) **Get-ImpHash * -algorithm <algorithm>**
   
   > Get-ImpHash * -algorithm sha256

3) **Get-ImpHash <file_path> -ShowTable**
   
   >Print the IAT Table as strings. (Default print is seperated by spaces, add Delimiter '-d' to print the list the way you like)
   
4) **Get-ImpHash --help**
5) **Supported Algorithms:** SHA1, SHA256, SHA512, MD5. (Default => MD5)
   
# 
   
+ ### Get-ExpHash Command:

1) **Get-ExpHash <file_path> -algorithm <algorithm> -ShowTable -delimiter 'delimiter'**
    
   > Get-ExpHash c:\windows\system32\kernel32.dll -a sha256 -ShowTable -d ' | '
2) **Get-ExpHash * -algorithm <algorithm>**
   
   > Get-ExpHash * -algorithm sha256

3) **Get-ImpHash <file_path> -ShowTable**
   
   >Print the EAT Table as strings. (Default print is seperated by spaces, add Delimiter '-d' to print the list the way you like)
   
4) **Get-ExpHash --help**
5) **Supported Algorithms:** SHA1, SHA256, SHA512, MD5. (Default => SHA256)
