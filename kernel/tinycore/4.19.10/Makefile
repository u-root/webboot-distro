all:
	wget http://tinycorelinux.net/10.x/x86/release/src/kernel/linux-4.19.10-patched.txz
	tar xvf linux-*txz
	(cp config-* linux-4.19.10/.config && cd linux-4.19.10 && make oldconfig && make -j 8 bzImage)
	cp linux-4.19.10/arch/x86/boot/bzImage .
clean:
	rm -rf linux-4.19.10*

