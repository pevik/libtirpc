SUBDIRS = src man doc
ACLOCAL_AMFLAGS = -I m4

GENFILES	       = tirpc/rpcsvc/crypt.h \
			 tirpc/rpcsvc/mount.h \
			 tirpc/rpcsvc/nfs_prot.h \
			 tirpc/rpcsvc/rquota.h \
			 tirpc/rpc/rpcb_prot.h

noinst_HEADERS	       = tirpc/reentrant.h \
			 tirpc/getpeereid.h \
			 tirpc/libc_private.h \
			 tirpc/un-namespace.h

nobase_include_HEADERS = tirpc/netconfig.h \
			 tirpc/rpcsvc/crypt.x \
			 tirpc/rpcsvc/mount.x \
			 tirpc/rpcsvc/nfs_prot.x \
			 tirpc/rpcsvc/rquota.x \
			 tirpc/rpc/xdr.h \
			 tirpc/rpc/types.h \
			 tirpc/rpc/svc_soc.h \
			 tirpc/rpc/svc.h \
			 tirpc/rpc/svc_dg.h \
			 tirpc/rpc/svc_auth.h \
			 tirpc/rpc/svc_mt.h \
			 tirpc/rpc/rpc_msg.h \
			 tirpc/rpc/rpc.h \
			 tirpc/rpc/rpcent.h \
			 tirpc/rpc/rpc_com.h \
			 tirpc/rpc/rpcb_prot.x \
			 tirpc/rpc/rpcb_clnt.h \
			 tirpc/rpc/raw.h \
			 tirpc/rpc/pmap_rmt.h \
			 tirpc/rpc/pmap_prot.h \
			 tirpc/rpc/pmap_clnt.h \
			 tirpc/rpc/nettype.h \
			 tirpc/rpc/key_prot.h \
			 tirpc/rpc/des.h \
			 tirpc/rpc/des_crypt.h \
			 tirpc/rpc/clnt_stat.h \
			 tirpc/rpc/clnt_soc.h \
			 tirpc/rpc/clnt.h \
			 tirpc/rpc/auth_unix.h \
			 tirpc/rpc/auth_des.h \
			 tirpc/rpc/auth.h

if GSS
nobase_include_HEADERS += \
			 tirpc/rpc/rpcsec_gss.h \
			 tirpc/rpc/auth_gss.h \
			 tirpc/rpc/svc_auth_gss.h
endif

pkgconfigdir=$(libdir)/pkgconfig
pkgconfig_DATA = libtirpc.pc

nobase_nodist_include_HEADERS = $(GENFILES)
BUILT_SOURCES = $(GENFILES)

$(GENFILES): %.h: %.x
	mkdir -p $(dir $@)
	rpcgen -h -o $@ $<

force:

CLEANFILES	       = cscope.* *~ $(GENFILES)
DISTCLEANFILES	       = Makefile.in libtirpc*.tar.gz
