
CC = gcc
FLAGS = -I ./NtyCo/core/ -L ./NtyCo/ -lntyco -lpthread -ldl
SRCS  = kvstore.c kvstore_array.c epoll_entry.c  nty_entry.c  kvstore_rbtree.c kvstore_hash.c
TESTCASE_SRCS =testcase.c

TARGET   = kvstore
SUBDIR = ./NtyCo/
TESTCASE = testcase

OBJS = $(SRCS:.c=.o)

all: $(SUBDIR) $(TARGET) $(TESTCASE)

$(SUBDIR): ECHO
	make -C $@
ECHO:
	@echo $(SUBDIR)

$(TARGET):$(OBJS)
	$(CC) -o $@ $^ $(FLAGS)

$(TESTCASE):$(TESTCASE_SRCS)
	$(CC) -o $@ $^

%.o: %.c
	$(CC) $(FLAGS) -c $^ -o $@

clean:
	rm -rf $(OBJS) $(TARGET) $(TESTCASE)
	