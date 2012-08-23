# Building LevelDB On Windows

Install the [Windows Software Development Kit version 7.1](http://www.microsoft.com/downloads/dlx/en-us/listdetailsview.aspx?FamilyID=6b6c21d2-2006-4afa-9702-529fa782d63b).

1. Open the "Windows SDK 7.1 Command Prompt" :
   Start Menu -> "Microsoft Windows SDK v7.1" > "Windows SDK 7.1 Command Prompt"

2. Change the directory to the leveldb project

3. To build a static 32 bit lib, run: 

    setenv /x86
    msbuild /p:Configuration=Release /p:Platform=Win32

4. To build a static 64 bit lib, run: 

    setenv /x64
    msbuild /p:Configuration=Release /p:Platform=x64




