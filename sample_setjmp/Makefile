
PS2_IP = 192.168.0.100
TIMEOUT = 4

EE_BIN = mini_luap.elf

EE_OBJS = mini_luap.o

EE_LIBS   += -L$(PS2SDK)/ports/lib -L../lib -ldebug -llua
EE_INCS   += -I../include -Iinclude -I$(PS2SDK)/ports/include -I../src

all: $(EE_BIN)

clean:
	rm -f $(EE_BIN) $(EE_OBJS)

tests: $(EE_BIN)
	ps2client -t $(TIMEOUT) -h $(PS2_IP) execee host:$(EE_BIN)
	ps2client -h $(PS2_IP) reset

reset:
	ps2client -h $(PS2_IP) reset

include $(PS2SDK)/samples/Makefile.pref
include $(PS2SDK)/samples/Makefile.eeglobal
