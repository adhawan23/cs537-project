.PHONY: all
all : libcrawler.so file_tester web_tester

file_tester : file_tester.c libcrawler.so
	gcc -L. -lcrawler -lpthread file_tester.c -Wall -Werror -o file_tester

web_tester : web_tester.c cs537.c libcrawler.so
	gcc -L. -lcrawler -lpthread web_tester.c cs537.c -Wall -Werror -o web_tester

libcrawler.so : crawler.c
	gcc -fpic -c crawler.c -Wall -Werror -o crawler.o
	gcc -shared -o libcrawler.so crawler.o

.PHONY: clean
clean :
	rm -f file_tester web_tester libcrawler.so *.o *.dSYM *~

.PHONY: test
test :
	~cs537-1/ta/tests/4a/runtests -c
	rm -f *.log