# Copyright 2015 University of Rochester
# 
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
# 
#   http://www.apache.org/licenses/LICENSE-2.0
# 
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.


EXTRA_CFLAGS := -I$(src)/../include
obj-m += sysextend.o
sysextend-objs := sysextend_rootkit.o sysextend_table.o sysextend_main.o

all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules
	mv -f *.o ./obj || true
	mv -f .*.cmd ./obj || true
	mv -f *.mod.c ./obj || true
	mv -f Module.symvers ./obj || true
	mv -f modules.order ./obj || true
	mv -f *.ko ./kobj || true

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
