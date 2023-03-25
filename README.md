# hello-kmod

## Setup
~~~
sudo dnf install kernel-devel kernel-headers
~~~

## Compile
~~~
make
~~~

## Validate
~~~
$ modinfo hello.ko
filename:       /home/nick/workspace/hello-kmod/hello.ko
license:        GPL
depends:        
retpoline:      Y
name:           hello
vermagic:       6.2.7-200.fc37.x86_64 SMP preempt mod_unload 
~~~

## Install
~~~
$ sudo insmod ./hello.ko 
$ sudo journalctl
[...]
Mar 24 20:20:09 fedora kernel: Hello world.
~~~

## Uninstall
~~~
$ sudo rmmod hello.ko
$ sudo journalctl
[...]
Mar 24 20:21:28 fedora kernel: Goodbye world.
~~~
