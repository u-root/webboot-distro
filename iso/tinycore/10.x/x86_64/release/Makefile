all:
	 wget http://tinycorelinux.net/10.x/x86_64/release/TinyCorePure64-current.iso
	 sudo mount -o loop TinyCorePure64-current.iso /mnt/cdrom/
	 mkdir /tmp/iso
	 rsync -av /mnt/cdrom/ /tmp/iso
	 sudo cp ../../../../../kernel/tinycore/4.19.10/bzImage /tmp/iso/boot/vmlinuz64 
	 sudo mkisofs -o webboot.iso -b boot/isolinux/isolinux.bin -c boot/isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -R -V webboot /tmp/iso
