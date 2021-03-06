#
# Copyright (C) 2016 Glyptodon, Inc.
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
# THE SOFTWARE.
#

AUTOMAKE_OPTIONS = foreign 

bin_PROGRAMS = guacenc

man_MANS =        \
    man/guacenc.1

noinst_HEADERS =    \
    buffer.h        \
    display.h       \
    encode.h        \
    ffmpeg-compat.h \
    guacenc.h       \
    image-stream.h  \
    instructions.h  \
    jpeg.h          \
    layer.h         \
    log.h           \
    parse.h         \
    png.h           \
    video.h

guacenc_SOURCES =           \
    buffer.c                \
    display.c               \
    display-buffers.c       \
    display-image-streams.c \
    display-flatten.c       \
    display-layers.c        \
    display-sync.c          \
    encode.c                \
    guacenc.c               \
    image-stream.c          \
    instructions.c          \
    instruction-blob.c      \
    instruction-cfill.c     \
    instruction-copy.c      \
    instruction-cursor.c    \
    instruction-dispose.c   \
    instruction-end.c       \
    instruction-img.c       \
    instruction-move.c      \
    instruction-rect.c      \
    instruction-shade.c     \
    instruction-size.c      \
    instruction-sync.c      \
    instruction-transfer.c  \
    jpeg.c                  \
    layer.c                 \
    log.c                   \
    parse.c                 \
    png.c                   \
    video.c

# Compile WebP support if available
if ENABLE_WEBP
guacenc_SOURCES += webp.c
noinst_HEADERS  += webp.h
endif

guacenc_CFLAGS =            \
    -Werror -Wall -pedantic \
    @AVCODEC_CFLAGS@        \
    @AVUTIL_CFLAGS@         \
    @LIBGUAC_INCLUDE@       \
    @SWSCALE_CFLAGS@

guacenc_LDADD =     \
    @LIBGUAC_LTLIB@

guacenc_LDFLAGS =  \
    @AVCODEC_LIBS@ \
    @AVUTIL_LIBS@  \
    @CAIRO_LIBS@   \
    @JPEG_LIBS@    \
    @SWSCALE_LIBS@ \
    @WEBP_LIBS@

EXTRA_DIST =      \
    man/guacenc.1

