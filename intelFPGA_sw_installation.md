## Installing ModelSim:

If you get the following error:
```
vish: error while loading shared libraries: libXext.so.6: cannot open shared object file: No such file or directory
```
This means that the 32 bit deps are missing. Try the following:
```
sudo apt-get install libxrender1:i386 libxtst6:i386 libxi6:i386 libxft2 libxft2:i386
```
