# Asus Zenbook ux3402za sound fix under Linux

* edit ssdt.dsl if needed 

## Build the DSDT patch

```iasl -tc ssdt.dsl```

## Copy the `aml` into /boot

```sudo cp -f ssdt.aml /boot```

## Copy grub script and make it executable

```sudo cp -f 01_acpi /etc/grub.d```

```sudo chmod +x /etc/grub.d/01_acpi```

## Update grub config

```sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg```

OR 

```sudo grub2-mkconfig -o /boot/grub2/grub.cfg```

> May also need to disable secure boot. (I had to in Fedora)

## Reboot and enjoy
