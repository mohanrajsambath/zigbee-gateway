#DEVICE = COORDINATOR
DEVICE = ROUTER
#DEVICE = ENDDEV

#Relative project path
PROJ_DIR = 

INCLUDE = -I$(PROJ_DIR)../../../../server/Source  -I$(PROJ_DIR)../../Source -I$(PROJ_DIR)../Source
LIBS = -lpthread

#CC= /data/opt/vendors/codesourcery/lite/arm-2009q1-203/bin/arm-none-linux-gnueabi-gcc
CC= gcc
#CC=arm-angstrom-linux-gnueabi-gcc
#CC=arm-none-linux-gnueabi-gcc
#CC=/usr/local/angstrom/arm/bin/arm-angstrom-linux-gnueabi-gcc

CFLAGS= -c -Wall -g -std=gnu99

all: simpleIHD.bin

simpleIHD.bin: simpleIHD.o socket_client.o
	$(CC) simpleIHD.o socket_client.o $(LIBS) -o simpleIHD.bin

# rule for file "simpleIHD.o".
simpleIHD.o: ../Source/simpleIHD.c
	$(CC) $(CFLAGS) $(INCLUDE) $(DEFS) ../Source/simpleIHD.c

# rule for file "socket_client.o".
socket_client.o: $(PROJ_DIR)../../Source/socket_client.h $(PROJ_DIR)../../Source/socket_client.c
	$(CC) $(CFLAGS) $(INCLUDE) $(DEFS) $(PROJ_DIR)../../Source/socket_client.c

# rule for cleaning files generated during compilations.
clean:
	/bin/rm -f simpleIHD.bin *.o
