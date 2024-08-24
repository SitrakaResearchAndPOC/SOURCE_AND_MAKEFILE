# INSTALLATION DEPENDANCES

```  
apt install build-essential
```  
```  
apt install libc6-dev
```  
```  
apt install libc-dev-bin
```  
```  
apt install manpages-dev
```  
```  
apt install git zip gcc zsh
```  
```  
apt install nano gedit mousepad
```  
```  
apt install rpcbind
```
```  
apt install zip
```  
```  
apt install git
```  
```  
apt install nano mousepad
```  
```  
apt install make 
```  
# EXERCICE HELLO WORLD
```
mkdir TPC
```
```
cd TPC/
```
```
nano helloworld.c
```
Copier le code suivant puis tapez ctrl+x et Y et enter pour enregistrer
```
#include <stdio.h>
#include <stdlib.h>

void main(){
	printf("hello world\n");
}
```
```
gcc -c helloworld.c
```
```
gcc -o helloworld helloworld.o
```
```
chmod +x helloworld
```
```
./helloworld
 ```
```
exit
```
# EXERCICE DIFF
```
mkdir TP_DIFF
```
```
cd TP_DIFF
```
```
nano helloworld.c
```
Copier le code suivant puis tapez ctrl+x et Y et enter pour enregistrer
```
#include <stdio.h>
#include <stdlib.h>

void main(){
	printf("hello world\n");
}
```
```
nano helloworld_version2.c
```
Copier le code suivant puis tapez ctrl+x et Y et enter pour enregistrer
```
#include <stdio.h>
#include <stdlib.h>

void main(){
	printf("hello world version2\n");
}
```
```
diff -u helloworld.c helloworld_version2.c > helloworld.diff
```
```
gedit helloworld.diff
```
```
patch -p0 helloworld.c < helloworld.diff
```
```
gedit helloworld.c
```




# EXERCICE MAKE FILE : 
Vérifier vraiment que vous utilisez une tabulation et non
# Reponse Makefile.1 : Makefile type 1
```
mkdir TP_MAKEFILE
```
```
cd TP_MAKEFILE
```
```
mkdir TP_MAKEFILE1
```
```
git clone https://github.com/SitrakaResearchAndPOC/FullRPC_LXD 
```
```
mv FullRPC_LXD/*.c TP_MAKEFILE1
```
```
mv FullRPC_LXD/*.h TP_MAKEFILE1
```
```
rm -rf FullRPC_LXD
```
```
cd TP_MAKEFILE1
```
```
nano Makefile
```
Copier et Enregistrer
```
all: exec

main.o: main.c tri.h
        gcc -c main.c -o main.o

fonction_tri.o: fonction_tri.c tri.h
                gcc -c fonction_tri.c -o fonction_tri.o

fonction_tableau.o: fonction_tableau.c tri.h
                        gcc -c fonction_tableau.c -o fonction_tableau.o

exec: fonction_tableau.o fonction_tri.o main.o
        gcc fonction_tableau.o fonction_tri.o main.o -o exec

clean:
        rm -rf *.o
        rm -rf exec
```
```
make all
```
```
chmod +x exec 
```
```
./exec 
```
```
make clean
```
```
cd ..
```
```
exit
```
MAKEFILEHOATAO
# Reponse 5.2 : TP_MAKEFILE2
```
cd TP_MAKEFILE
```
```
mkdir TP_MAKEFILE2
```
```
git clone https://github.com/SitrakaResearchAndPOC/FullRPC_LXD 
```
```
mv FullRPC_LXD/*.c TP_MAKEFILE2
```
```
mv FullRPC_LXD/*.h TP_MAKEFILE2
```
```
rm -rf FullRPC_LXD
```
```
cd TP_MAKEFILE2
```
```
nano Makefile
```
Copier et Enregistrer
```
all: exec

main.o: main.c tri.h
         gcc -c $< -o $@

fonction_tri.o: fonction_tri.c tri.h
         gcc -c $< -o $@

fonction_tableau.o: fonction_tableau.c tri.h
         gcc -c $< -o $@

exec: fonction_tableau.o fonction_tri.o main.o
        gcc $^ -o $@

clean:
        rm -rf *.o
        rm -rf exec
```
```
make all
```
```
chmod +x  exec
```
```
./exec 
```
```
make clean
```
```
cd ..
```
```
exit
```

# reponse 5.3 : TP_MAKEFILE3
```
cd TP_MAKEFILE
```
```
mkdir TP_MAKEFILE3
```
```
git clone https://github.com/SitrakaResearchAndPOC/FullRPC_LXD
```
```
mv FullRPC_LXD/*.c TP_MAKEFILE3
```
```
mv FullRPC_LXD/*.h TP_MAKEFILE3
```
```
rm -rf FullRPC_LXD
```
```
cd TP_MAKEFILE3
```
```
nano Makefile
```
Copier et Enregistrer
```
CC=gcc
SRC=$(wildcard *.c)
OBJ=$(SRC:.c=.o)
all: exec

main.o: main.c tri.h
         $(CC) -c $< -o $@

fonction_tri.o: fonction_tri.c tri.h
         $(CC) -c $< -o $@

fonction_tableau.o: fonction_tableau.c tri.h
         $(CC) -c $< -o $@

exec: $(OBJ)
        $(CC) $^ -o $@

clean:
        rm -rf *.o
        rm -rf exec
```
```
make all
```
```
chmod +x exec 
```
```
./exec 
```
```
make clean
```
```
cd ..
```
```
exit
```

# reponse 5.4 : TP_MAKEFILE4
```
cd TP_MAKEFILE
```
```
mkdir TP_MAKEFILE4
```
```
git clone https://github.com/SitrakaResearchAndPOC/FullRPC_LXD 
```
```
mv FullRPC_LXD/*.c TP_MAKEFILE4
```
```
mv FullRPC_LXD/*.h TP_MAKEFILE4
```
```
rm -rf FullRPC_LXD
```
```
cd TP_MAKEFILE4
```
```
nano Makefile
```
Copier et Enregistrer
```
CC=gcc
SRC=$(wildcard *.c)
OBJ=$(SRC:.c=.o)
all: exec

%.o: %.c tri.h
        $(CC) -c $< -o $@

exec: $(OBJ)
        $(CC) $^ -o $@

clean:
        rm -rf *.o
        rm -rf exec
```
```
make all
```
```
chmod +x exec
```
```
./exec 
```
```
make clean
```
```
cd ..
```
```
exit
```
# exercice 5.5 : à faire
* [Makefile](https://www.cs.colby.edu/maxwell/courses/tutorials/maketutor/)
* [Makefile_pdf](https://github.com/SitrakaResearchAndPOC/FullRPC_LXD/blob/main/A%20Simple%20Makefile%20Tutorial.pdf)


