

main: merch.h main.c webstore.c webstore.h merch.c merch.h
	gcc -g -Wall -pedantic -std=c11 list_linked.c common.c iterator.c \
	hash_table.c webstore.c utils.c merch.c main.c -o ./bin
	@echo "::::::::::: Finished :::::::::::"


dbg: debug.c webstore.c webstore.h merch.h merch.c
	gcc -g -Wall -pedantic -std=c11 list_linked.c common.c iterator.c \
	hash_table.c webstore.c utils.c debug.c merch.c -o ./dbg 
	./dbg
	@echo "::::::::::: Finished :::::::::::"

run:
	./dbg

dbgt: dbg
	valgrind --leak-check=full ./dbg
cart:
	gcc cart.c utils.c common.c hash_table.c list_linked.c webstore.c iterator.c

clean:
	rm ./main
	@echo "Removed Binary"


run: main
	./bin

test: 
	gcc -g -Wall -std=c11 list_linked.c common.c iterator.c \
	hash_table.c webstore.c utils.c  test.c -lcunit  -o ./bin

memtest: test
	valgrind --leak-check=full ./bin
	
test_cart: 
	gcc -g -Wall -std=c11 list_linked.c common.c iterator.c \
	hash_table.c webstore.c utils.c cart.c test_cart.c -lcunit  -o ./bin

memtest_cart: test_cart
	valgrind --leak-check=full ./bin

runl: main
	./bin -l


rund: main
	./bin --log --debug

help:
	@printf "=Commands=\t=Description=\n"
	@printf "make test\tRun with testing\n"
	@printf "make main\tRemove binary and compile\n"
	@printf "make clean\tRemove binary\n"
	@printf "make run\tRun (No Arguments)\n"
	@printf "make runl\tRun (With Logging)\n"
	@printf "make rund\tRun (With Logging and Debugging)\n"
	@printf "make help\tDisplay this message\n"
