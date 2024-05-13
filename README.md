**

# Open GL (feeGlut) install in Windows With Visual Studio Code

**
YouTube Tutorial Guide: 

Step:

- Download VS Code (https://code.visualstudio.com/download)

- Download MSYS2 (https://www.msys2.org/)

- Generate and Download Glad (https://glad.dav1d.de/) with the latest version(4.6)

- Install VS Code

- Install MSYS2

- Put Glad on MSYS2

- Edit Environment Variables for MSYS2

- Configure VS Code

  - Download Extension(C++)

  - Add IncludePath

MSYS2 MINGW command:

    pacman -Syu
    
    pacman -S mingw-w64-x86_64-toolchain
    
    pacman -S mingw-w64-x86_64-glew
    
    pacman -S mingw-w64-x86_64-glfw
    
    pacman -S mingw-w64-x86_64-freeglut



VS Code Extension

- C/C++

- Code Runner





C/C++ Include path:(Settings)

    ${env:MSYS2}/mingw64/include/



Create Example File main.cpp

//Write your openGL code



run in terminal: `g++ minar.cpp -o minar -lopengl32 -lfreeglut -lglu32 -lglew32 -lglfw3 -lgdi32 -lmingw32`

execute in terminal: ./main


Additional: 
VSCODE Configuration
**Executor Map

    "code-runner.executorMap": {
            "cpp": "cd $dir && g++ $env:MSYS2/mingw64/include/glad/glad.c (Get-ChildItem -Path . -Filter *.cpp -Recurse).FullName -o main -lopengl32 -lfreeglut -lglu32 -lglew32 -lglfw3 -lgdi32 -lmingw32 && ./main"
    },
