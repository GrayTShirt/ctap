AM_CPPFLAGS = -I$(srcdir)/../src
LDADD = $(top_builddir)/src/libctap.la

TESTS = 00-asserts.t 01-fail.t 02-skip.t 03-todo.t 04-bail.t 05-premature.t 06-output.t 07-stack.t 08-printf.t 09-fork.t
check_PROGRAMS = 00-asserts.t 01-fail 02-skip.t 03-todo.t 04-bail 05-premature 06-output 07-stack 08-printf 09-fork
00_asserts_t_SOURCES = 00-asserts.c   ../src/ctap.h
01_fail_SOURCES      = 01-fail.c      ../src/ctap.h
02_skip_t_SOURCES    = 02-skip.c      ../src/ctap.h
03_todo_t_SOURCES    = 03-todo.c      ../src/ctap.h
04_bail_SOURCES      = 04-bail.c      ../src/ctap.h
05_premature_SOURCES = 05-premature.c ../src/ctap.h
06_output_SOURCES    = 06-output.c    ../src/ctap.h
07_stack_SOURCES     = 07-stack.c     ../src/ctap.h
08_printf_SOURCES    = 08-printf.c    ../src/ctap.h
09_fork_SOURCES      = 09-fork.c      ../src/ctap.h

EXTRA_DIST = extap untap expect skips 01-fail.t 04-bail.t 05-premature.t 06-output.t 07-stack.t 08-printf.t 09-fork.t

###########################################

if GCOV_ENABLED
coverage-clean:
	@rm -fr coverage
	@find . -name "*.gcda" -exec rm {} \;
	@lcov --directory . --zerocounters

coverage-report:
	@mkdir -p coverage
	@lcov --compat-libtool --directory .. --capture --output-file coverage/app.info
	@genhtml -o coverage/ coverage/app.info

coverage:
	@make coverage-report

clean-local:
	@make coverage-clean

check:
	@make coverage

.PHONY: coverage-clean coverage-report coverage
endif
