all:	asmsx

CC=gcc
CCOSX=o64-clang
c_files=dura.tab.c lex.yy.c lex.parser1.c lex.parser2.c lex.parser3.c asmsx.c\
		labels.c
OPT=-lm -O2 -Os -s -Wall -Wextra
VERSION=0.19.2

HEADERS= asmsx.h labels.h

asmsx:  $(c_files) $(HEADERS)
	$(CC) $(c_files) -o$@ $(OPT)
asmsx.osx:  $(c_files) $(HEADERS)
	$(CCOSX) $(c_files) -o$@ $(OPT)
asmsx-debug:	$(c_files) $(HEADERS) dura.y
	bison --graph -t -d dura.y
	$(CC) -ggdb $(c_files) -o$@ -lm -Os -Wall -Wextra
asmsx.exe: $(c_files) $(HEADERS)
	i686-w64-mingw32-gcc $(c_files) -o$@ $(OPT)
release: asmsx asmsx.exe asmsx.osx
	zip asmsx_$(VERSION)_linux64.zip asmsx
	zip asmsx_$(VERSION)_win32.zip asmsx.exe
	zip asmsx_$(VERSION)_macOS64.zip asmsx.osx

dura.tab.c dura.tab.h:	dura.y
	bison -d $<
lex.yy.c:	lex.l
	flex -i $<
lex.parser1.c:	parser1.l
	flex -i -Pparser1 $<
lex.parser2.c:	parser2.l
	flex -i -Pparser2 $<
lex.parser3.c:	parser3.l
	flex -i -Pparser3 $<
clean:
	rm -f *.o *.tab.* lex.*.c asmsx asmsx-debug test *.exe ~* *.osx asmsx_*.zip
test:	test.cpp asmsx.c labels.c $(HEADERS)
	gcc -c asmsx.c labels.c $(OPT)
	g++ -o test labels.o asmsx.o test.cpp -L/usr/local/lib -lgtest -lgtest_main -lpthread $(OPT)
	./test
install:	asmsx
	sudo cp asmsx /usr/local/bin

