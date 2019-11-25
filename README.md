## call plink
```
F:\_Tmp\Personal\plink.exe -serial COM3 -sercfg 9600,8,n,1,X
```

## complete Arduino
```
NPP_SAVE
"C:\Users\dwa\Desktop\arduino-1.8.10\arduino_debug.exe" --verify "$(FULL_CURRENT_PATH)"
```

## upload Arduino
```
NPP_SAVE
"C:\Users\dwa\Desktop\arduino-1.8.10\arduino_debug.exe" --upload "$(FULL_CURRENT_PATH)"
```

### Run Python 
```
NPP_SAVE
C:\Program Files (x86)\Microsoft Visual Studio\Shared\Python37_64\python.exe "$(FULL_CURRENT_PATH)"
```

### ASSEMBLY
```
npp_save
npp_run cmd /K (cd /D "$(CURRENT_DIRECTORY)" && C:\Dev\Masm615\make32.bat $(NAME_PART) && cls && $(NAME_PART))
```

### ASSEMBLY 16Bit
```
npp_save
npp_run cmd /K (cd /D "$(CURRENT_DIRECTORY)" && C:\Dev\Masm615\make16.bat $(NAME_PART))
"C:\Program Files (x86)\DOSBox-0.74\DOSBox.exe"  "$(CURRENT_DIRECTORY)"
```

### AutoPEP8
```
npp_save
autopep8 --in-place --aggressive --aggressive  "$(FULL_CURRENT_PATH)"
```

### C++ Compile
```
npp_save
g++ -m32 "$(FULL_CURRENT_PATH)" -o "$(CURRENT_DIRECTORY)\$(NAME_PART).exe"  -std=c++11
npp_run cmd /K (cd /D "$(CURRENT_DIRECTORY)" && "$(NAME_PART).exe" && pause)
```

### C++ to Assembly
```
npp_save
g++ "$(FULL_CURRENT_PATH)" -S -o "$(CURRENT_DIRECTORY)\$(NAME_PART).asm"  -std=c++11
```

### C++ to MASM
```
npp_save
gcc "$(FULL_CURRENT_PATH)" -masm=intel -S -o "$(CURRENT_DIRECTORY)\$(NAME_PART).asm"
```

### Dot Lang Compile
```
npp_save
dot -Tpdf "$(FULL_CURRENT_PATH)" > "$(CURRENT_DIRECTORY)\$(NAME_PART).pdf"
"$(CURRENT_DIRECTORY)\$(NAME_PART).pdf"
```

### Python
```
npp_save
npp_run python "$(FULL_CURRENT_PATH)"
pause
```

### Python C Compiler
```
npp_save
g++ "$(FULL_CURRENT_PATH)" -std=c++11 -o "$(CURRENT_DIRECTORY)\$(NAME_PART).exe" -I C:\Dev\Python27\include 
npp_run cmd /K (cd /D "$(CURRENT_DIRECTORY)" && "$(NAME_PART).exe" && pause)
```

### Python Debug
```
npp_save
python "$(FULL_CURRENT_PATH)"
```

### Python Tidy
```
npp_save
python c:/dev/python27/PythonTidy.py "$(FULL_CURRENT_PATH)"
```
