include ../build_config.mk

OBJS += ../src/link.o ../src/util/fde.o ../src/util/log.o ../src/util/bytes.o
CFLAGS += -I../src
EXES = ssdb-bench ssdb-dump ssdb-repair leveldb-import

all: ssdb-bench.o ssdb-dump.o ssdb-repair.o leveldb-import.o
	${CXX} -o ssdb-bench ssdb-bench.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
	${CXX} -o ssdb-dump ssdb-dump.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
	${CXX} -o ssdb-repair ssdb-repair.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
	${CXX} -o leveldb-import leveldb-import.o ${OBJS} ${UTIL_OBJS} ${CLIBS}

ssdb-bench.o: ssdb-bench.cpp
	${CXX} ${CFLAGS} -c ssdb-bench.cpp
ssdb-dump.o: ssdb-dump.cpp
	${CXX} ${CFLAGS} -c ssdb-dump.cpp
ssdb-repair.o: ssdb-repair.cpp
	${CXX} ${CFLAGS} -c ssdb-repair.cpp
leveldb-import.o: leveldb-import.cpp
	${CXX} ${CFLAGS} -c leveldb-import.cpp

clean:
	rm -f *.exe *.exe.stackdump *.o ${EXES}
	rm -rf _cpy_

