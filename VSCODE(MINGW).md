### 配置
#### The new(24_12_3)
tasks
```
{

  

     "version": "2.0.0",

        "tasks": [

            {

                "type": "cppbuild",

                "label": "build_debug",

                "command": "D:/Enviroment/mingw64/bin/g++.exe",

                "args": [

                    "-fdiagnostics-color=always",

                    "-g",

                    "${file}",

                    "-o",

                    "${fileDirname}\\${fileBasenameNoExtension}_debug.exe"

                ],

                "options": {

                    "cwd": "D:/Enviroment/mingw64/bin"

                },

                "problemMatcher": [

                    "$gcc"

                ],

                "group": "build",

                "detail": "编译器: D:/Enviroment/mingw64/bin/g++.exe"

            },

            {

                "type": "cppbuild",

                "label": "build_release",

                "command": "D:/Enviroment/mingw64/bin/g++.exe",

                "args": [

                    "-O2",

                    "-fdiagnostics-color=always",

                    //"-g",

                    "${file}",

                    "-o",

                    "${fileDirname}\\${fileBasenameNoExtension}_release.exe"

                ],

                "options": {

                    "cwd": "D:/Enviroment/mingw64/bin"

                },

                "problemMatcher": [

                    "$gcc"

                ],

                "group": "build",

                "detail": "编译器: D:/Enviroment/mingw64/bin/g++.exe"

            },

  

        ]

    }
```
launch
```
{

  

        "version": "2.0.0",

        "configurations": [

        {

            "name": "Debug_app",

            "type": "cppdbg",

            "request": "launch",

            "program": "${fileDirname}\\${fileBasenameNoExtension}_debug.exe",

            "args": [],

            "stopAtEntry": false,

            "cwd": "${fileDirname}",

            "environment": [],

            "externalConsole": true,

            "MIMode": "gdb",

            "miDebuggerPath": "D:/Enviroment/mingw64/bin/gdb.exe",

            "setupCommands": [

                {

                    "description": "为 gdb 启用整齐打印",

                    "text": "-enable-pretty-printing",

                    "ignoreFailures": true

                },

                {

                    "description": "将反汇编风格设置为 Intel",

                    "text": "-gdb-set disassembly-flavor intel",

                    "ignoreFailures": true

                }

            ],

            "preLaunchTask": "build_debug"

        },

        {

            "name": "Release_app",

            "type": "cppdbg",

            "request": "launch",

            "program": "${fileDirname}\\${fileBasenameNoExtension}_release.exe",

            "args": [],

            "stopAtEntry": false,

            "cwd": "${fileDirname}",

            "environment": [],

            "externalConsole": true,

            "MIMode": "gdb",

            "miDebuggerPath": "D:/Enviroment/mingw64/bin/gdb.exe",

            "setupCommands": [

                {

                    "description": "为 gdb 启用整齐打印",

                    "text": "-enable-pretty-printing",

                    "ignoreFailures": true

                },

                {

                    "description": "将反汇编风格设置为 Intel",

                    "text": "-gdb-set disassembly-flavor intel",

                    "ignoreFailures": true

                }

            ],

            "preLaunchTask": "build_release"

        },

  
  
  
  
  
  
  
  
  

        ],

    }
```
c_cpp_properties.json
```
{

    "configurations": [

        {

            "name": "windows-clang-x64",

            "includePath": [

                "${workspaceFolder}/**"

            ],

            "defines": [

                "_DEBUG",

                "UNICODE",

                "_UNICODE"

            ],

            "windowsSdkVersion": "10.0.22000.0",

            "compilerPath": "D:/Enviroment/mingw64/bin/g++.exe",

            "cStandard": "c17",

            "cppStandard": "c++17",

            "intelliSenseMode": "gcc-x64"

        }

    ],

    "version": 4

}
```
setting
```
{

  "C_Cpp_Runner.cCompilerPath": "D:/Enviroment/mingw64/bin/g++.exe",

  "C_Cpp_Runner.cppCompilerPath": "g++",

  "C_Cpp_Runner.debuggerPath": "gdb",

  "C_Cpp_Runner.cStandard": "c17",

  "C_Cpp_Runner.cppStandard": "c++17",

  "C_Cpp_Runner.msvcBatchPath": "C:/Program Files/Microsoft Visual Studio/VR_NR/Community/VC/Auxiliary/Build/vcvarsall.bat",

  "C_Cpp_Runner.useMsvc": false,

  "C_Cpp_Runner.warnings": [

    "-Wall",

    "-Wextra",

    "-Wpedantic",

    "-Wshadow",

    "-Wformat=2",

    "-Wcast-align",

    "-Wconversion",

    "-Wsign-conversion",

    "-Wnull-dereference"

  ],

  "C_Cpp_Runner.msvcWarnings": [

    "/W4",

    "/permissive-",

    "/w14242",

    "/w14287",

    "/w14296",

    "/w14311",

    "/w14826",

    "/w44062",

    "/w44242",

    "/w14905",

    "/w14906",

    "/w14263",

    "/w44265",

    "/w14928"

  ],

  "C_Cpp_Runner.enableWarnings": true,

  "C_Cpp_Runner.warningsAsError": false,

  "C_Cpp_Runner.compilerArgs": [],

  "C_Cpp_Runner.linkerArgs": [],

  "C_Cpp_Runner.includePaths": [

    "${workspaceFolder}/**"

  ],

  "C_Cpp_Runner.includeSearch": [

    "*",

    "**/*"

  ],

  "C_Cpp_Runner.excludeSearch": [

    "**/build",

    "**/build/**",

    "**/.*",

    "**/.*/**",

    "**/.vscode",

    "**/.vscode/**"

  ],

  "C_Cpp_Runner.useAddressSanitizer": false,

  "C_Cpp_Runner.useUndefinedSanitizer": false,

  "C_Cpp_Runner.useLeakSanitizer": false,

  "C_Cpp_Runner.showCompilationTime": false,

  "C_Cpp_Runner.useLinkTimeOptimization": false,

  "C_Cpp_Runner.msvcSecureNoWarnings": false

}
```
### 中文乱码
#### 方法1，语言设置 utf8-beta(其他软件solidworks，警告了一下，但能用)
#### 方法2, cmd,powershell 均修改为65001

##### 1. poweshell(以管理员模式运行)
```
 $OutputEncoding = [console]::InputEncoding = [console]::OutputEncoding = [System.Text.Encoding]::GetEncoding(65001);
```
##### 2. cmd设置编码为 utf-8
```

1、在运行中输入 regedit 找到 
HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Command Processor
2、右键--->>> 新建--->>>选择字符串值选项 --->>> “名称”列填写“autorun”, 数值数据填写“chcp 65001” (注意有空格)
3、重新打开 cmd 运行输入 chcp 查看当前的编码是否是 65001
```
