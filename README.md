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