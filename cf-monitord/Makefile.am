sbin_PROGRAMS = cf-monitord

AM_CPPFLAGS = @CPPFLAGS@ -I$(srcdir)/../libpromises \
	$(NOVA_CPPFLAGS)

if HAVE_NOVA
AM_CPPFLAGS += -I$(abs_top_srcdir)/nova/libcfmonitord
endif

AM_CFLAGS = @CFLAGS@ \
	$(NOVA_CFLAGS)

cf_monitord_LDADD = ../libpromises/libpromises.la
if HAVE_NOVA
cf_monitord_LDADD += ../nova/libcfmonitord/libcfmonitord.la
endif

cf_monitord_SOURCES = \
        verify_measurements.c \
        env_monitor.c env_monitor.h \
        mon.h \
        mon_cpu.c \
        mon_disk.c \
        mon_entropy.c \
        mon_load.c \
        mon_network_sniffer.c \
        mon_network.c \
        mon_processes.c \
        mon_temp.c \
        cf-monitord.c

CLEANFILES = *.gcno *.gcda

#
# Some basic clean ups
#
MOSTLYCLEANFILES = *~ *.orig *.rej
