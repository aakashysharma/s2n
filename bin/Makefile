#
# Copyright 2014 Amazon.com, Inc. or its affiliates. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License").
# You may not use this file except in compliance with the License.
# A copy of the License is located at
#
#  http://aws.amazon.com/apache2.0
#
# or in the "license" file accompanying this file. This file is distributed
# on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either
# express or implied. See the License for the specific language governing
# permissions and limitations under the License.
#

all: s2nc s2nd
include ../s2n.mk

ifeq ($(shell uname),Darwin)
    LIBS = 
else
    LIBS = -ldl -lrt -lpthread
endif

LDFLAGS += -L../lib/ -ls2n ${LIBS}
CRUFT += s2nc s2nd

s2nc: s2nc.c echo.c
	${CC} ${CFLAGS} s2nc.c echo.c  -o s2nc ${LDFLAGS}

s2nd: s2nd.c echo.c
	${CC} ${CFLAGS} s2nd.c echo.c -o s2nd ${LDFLAGS}
