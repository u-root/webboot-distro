# nasty Makefile, not intended to be used a lot.
# It is here for a record of how we did this.
# We leave things hanging around for the inevitable errors.
# Clean should get them all.
all: setup TinyCorePure64.iso CorePure64.iso
setup:
	mkdir -p cdrom tcpiso cpiso

TinyCorePure64.iso:
	mkdir -p tcpiso
	wget http://tinycorelinux.net/10.x/x86_64/release/TinyCorePure64-current.iso
	sudo mount -o loop TinyCorePure64-current.iso cdrom
	rsync -av cdrom/ tcpiso
	sudo umount cdrom
	sudo cp ../../../../../kernel/tinycore/4.19.10/bzImage tcpiso/boot/vmlinuz64 
	sudo mkisofs -o TinyCorePure64.iso -b boot/isolinux/isolinux.bin -c boot/isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -R -V webboot tcpiso

CorePure64.iso:
	mkdir -p cpiso
	wget http://tinycorelinux.net/10.x/x86_64/release/CorePure64-current.iso
	sudo mount -o loop CorePure64-current.iso cdrom
	rsync -av cdrom/ cpiso
	sudo umount cdrom
	sudo cp ../../../../../kernel/tinycore/4.19.10/bzImage cpiso/boot/vmlinuz64 
	sudo mkisofs -o CorePure64.iso -b boot/isolinux/isolinux.bin -c boot/isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -R -V webboot cpiso

clean:
	sudo rm -rf *-current* cdrom tcpiso cpiso
