CDIR := $(PWD)
TARGETDIR := $(CDIR)/bin

SRC := $(wildcard *.c)
OBJ := $(patsubst %.c,$(TARGETDIR)/%.o,$(SRC))

TARGET := $(TARGETDIR)/espresso

$(TARGETDIR)/%.o: %.c
	$(CC) $(CFLAGS) $(CPPFLAGS) -c -o $@ $<

all: prepare $(TARGET)

prepare:
	mkdir -p $(TARGETDIR)

$(TARGET): $(OBJ)
	$(LINK.c) $(OBJ) -o $(TARGET)

clean:
	@- $(RM) -r $(TARGETDIR)
	@- $(RM) $(OBJ)

