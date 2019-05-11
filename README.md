# ZonFS
This is a simple Storage Class Memory filesystem extended by Linux Ramfs.
The detail of ZonFS is discussed in the following paper:

**ZonFS: A Storage Class Memory File System with Memory Zone Partitioning on Linux** 
<br>
*Jang Woong Kim, Jae-Hoon Kim, Awais Khan, Youngjae Kim and Sungyong Park*<br>
Published in [AMGCC 2017][AMGCC]

**How to Use**
<br>
ZonFS repo is a complete Linux kernel directory.
1) Install the kernel just like you used to do make a kernel.
2) Mount ZonFS just like you mount ramfs, but the name of file system is "kimfs"
ex) mount -t kimfs -o size=512m kimfs /mnt/whatever

**Caveat**
1) ZonFS runs only on x86 machine.
2) You need to have at least 16GB DRAM.
If your machine has less than 16GB memory, modify STORAGE_ZONE_ADDRESS and STORAGE_ZONE_SIZE
defined in arch/x86/mm/init.c.
3) The 4.7.4 kernel, on which ZonFS is built, the maximum number of memory zones is 4.
Therefore, you can have at maximum three zones, thus saving one for ZonFS.

[AMGCC]: http://htcaas.kisti.re.kr/wiki/index.php/AMGCC17
