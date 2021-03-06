#
#  Copyright (c) 2016, Nest Labs, Inc.
#  All rights reserved.
#
#  Redistribution and use in source and binary forms, with or without
#  modification, are permitted provided that the following conditions are met:
#  1. Redistributions of source code must retain the above copyright
#     notice, this list of conditions and the following disclaimer.
#  2. Redistributions in binary form must reproduce the above copyright
#     notice, this list of conditions and the following disclaimer in the
#     documentation and/or other materials provided with the distribution.
#  3. Neither the name of the copyright holder nor the
#     names of its contributors may be used to endorse or promote products
#     derived from this software without specific prior written permission.
#
#  THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
#  AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
#  IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
#  ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE
#  LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
#  CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
#  SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
#  INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
#  CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
#  ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
#  POSSIBILITY OF SUCH DAMAGE.
#

include $(abs_top_nlbuild_autotools_dir)/automake/pre.am

bin_PROGRAMS                                                           = \
    ot-ncp                                                               \
    $(NULL)

ot_ncp_CPPFLAGS                                                        = \
    -I$(top_srcdir)/include                                              \
    -I$(top_srcdir)/examples/platforms                                   \
    $(NULL)

ot_ncp_LDADD                                                           = \
    $(top_builddir)/src/core/libopenthread.a                             \
    $(top_builddir)/src/ncp/libopenthread-ncp.a                          \
    $(top_builddir)/third_party/mbedtls/libmbedcrypto.a                  \
    $(NULL)

ot_ncp_LDFLAGS                                                         = \
    $(NULL)

if OPENTHREAD_ENABLE_DIAG
ot_ncp_LDADD                                                          += \
    $(top_builddir)/src/diag/libopenthread-diag.a                        \
    $(NULL)
endif

if OPENTHREAD_EXAMPLES_POSIX
ot_ncp_LDADD                                                          += \
    $(top_builddir)/examples/platforms/posix/libopenthread-posix.a       \
    -lstdc++                                                             \
    $(NULL)
endif

if OPENTHREAD_EXAMPLES_CC2538
ot_ncp_LDADD                                                          += \
    $(top_builddir)/examples/platforms/cc2538/libopenthread-cc2538.a     \
    $(NULL)

ot_ncp_LDFLAGS                                                        += \
    -T $(top_srcdir)/examples/platforms/cc2538/cc2538.ld                 \
    $(NULL)
endif

ot_ncp_SOURCES                                                         = \
    main.c                                                               \
    $(NULL)

include $(abs_top_nlbuild_autotools_dir)/automake/post.am
