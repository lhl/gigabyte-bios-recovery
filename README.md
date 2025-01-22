See:
- https://claude.ai/chat/eba52a74-aca1-485f-9bb2-9f083b737612
- https://chatgpt.com/c/678620df-93a8-8012-8f68-d391ec728fc4

# Clip
```
lsusb
Bus 003 Device 017: ID 1a86:5512 QinHeng Electronics CH341 in EPP/MEM/I2C mode, EPP/I2C adapter
```

- Turn off and unplug everything
- Match red strip to Pin 1 for clip
- Match 1/1 for the BIO section for the carrier board
- Assume that all the jumpers are set correctly


# Chip Info
```
🐟 ❯ sudo flashrom -p ch341a_spi
Enter Password or Place finger on fingerprint reader:
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
No operations were specified.
```

Backup
```
~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2) took 2s
🐟 ❯ sudo flashrom -p ch341a_spi -r backup.bin                                                   (base)
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
Reading flash... done.

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2) took 4m12s
🐟 ❯ sudo time flashrom -p ch341a_spi -r backup.bin2 -V                                          (base)
sudo: time: command not found

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ time sudo flashrom -p ch341a_spi -r backup.bin2 -V                                          (base)
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

flashrom was built with GCC 14.2.1 20240910, little endian
Command line (5 args): flashrom -p ch341a_spi -r backup.bin2 -V
Initializing ch341a_spi programmer
Device revision is 3.0.4
The following protocols are supported: SPI.
Probing for AMIC A25L010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L032, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L05PT, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L05PU, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L10PT, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L10PU, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L16PT, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L16PU, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L20PT, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L20PU, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L40PT, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L40PU, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L80P, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ032/A25LQ32A, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF011, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF021, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF021A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF041A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF081A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF321, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF321A, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF641(A), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DL081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DL161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DQ161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25F1024(A), 128 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F2048, 256 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F4096, 512 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512, 64 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512A, 64 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512B, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25FS010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25FS040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF041, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF321, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SL128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF041, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF081A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF161A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26F004, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45CS1282, 16896 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB011D, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB021D, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB041D, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB081D, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB161D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321C, 4224 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB642D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25D16A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25D80A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25Q64AS, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25Q128AS, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESMT F25L008A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESMT F25L32PA, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B05T, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B10T, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B16T, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B20T, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B32T, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B40T, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B64T, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B80T, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q32(A/B), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q80(A), 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH32B, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH64A, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F005, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F01, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F02(A), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F04(A), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q04, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q08, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25B128B/GD25Q128B, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF128E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ128E/GD25LB128E/GD25LR128E/GD25LQ128D/GD25LQ128C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ255E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ64(B), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB256E/GD25LR256E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB256F/GD25LR256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB512MF/GD25LR512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB512ME/GD25LR512ME, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q128E/GD25B128E/GD25R128E/GD25Q127C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q128C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q16(B), 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q20(B), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q256E/GD25B256E/GD25R256E/GD25Q256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25B512MF/GD25R512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q32(B), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q40(B), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q64(B), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q80(B), 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25T80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ16C, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ21B, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ40C, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ41B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ80C, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F64F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F128F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25WQ80E, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP064, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LQ016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP032, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP064, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WQ040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F160S33B8, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F160S33T8, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F320S33B8, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F320S33T8, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F640S33B8, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F640S33T8, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L12854, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L1654, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L3254, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L6454, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1005(C)/MX25L1006E, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12805D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12833F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12835F/MX25L12873F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12845E/MX25L12865E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12850F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V16066, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605A/MX25L1606E/MX25L1608E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605D/MX25L1608D/MX25L1673E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1635D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1633E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1635E/MX25L1636E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L2005(C)/MX25L2006E, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L25635F/MX25L25645G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Added layout entry 00000000 - 01ffffff named complete flash
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
Chip status register is 0x40.
Chip status register: Status Register Write Disable (SRWD, SRP, ...) is not set
Chip status register: Bit 6 is set
Chip status register: Block Protect 3 (BP3) is not set
Chip status register: Block Protect 2 (BP2) is not set
Chip status register: Block Protect 1 (BP1) is not set
Chip status register: Block Protect 0 (BP0) is not set
Chip status register: Write Enable Latch (WEL) is not set
Chip status register: Write In Progress (WIP/BUSY) is not set
Probing for Macronix MX25L3205(A), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3205D/MX25L3208D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3206E/MX25L3208E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3273F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3239E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3235D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3233F/MX25L3273E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3255E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L4005(A/C)/MX25L4006E, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L512(E)/MX25V512(C), 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L5121E, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6405, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6405D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6406E/MX25L6408E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6436E/MX25L6445E/MX25L6465E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6473E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6473F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6495F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L8005/MX25L8006E/MX25L8008E/MX25V8005, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R1635F, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R2035F, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R3235F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R4035F, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R6435F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R8035F, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V4035F, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V8035F, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V1635F, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U12835F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U1635E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25635F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25643G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25645G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U3235E/F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U51245G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U6435E/F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U8032E, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX66L51235F/MX25L51245G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX66L1G45G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX77L25650F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX77U51250F, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P05, 64 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P05-A, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P10, 128 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P10-A, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P20-old, 256 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P40-old, 512 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q00A..1G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q00A..3G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q032..1E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q032..3E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q064..1E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q064..3E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q128..1E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q128..3E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q256..1E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q256..3E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q512..1G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q512..3G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL01G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU01G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL02G, 262144 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU02G, 262144 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL512, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU512, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD010(C), 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD020(C), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD040(C), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD256C, 32 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD512(C), 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ032C, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV010, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for PMC Pm25LV010A, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV016B, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV512(A), 64 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for PUYA P25Q06H, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PUYA P25Q11H, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PUYA P25Q21H, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25LF020A, 256 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25LF040A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for SST SST25LF080(A), 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for SST SST25VF010(A), 128 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF016B, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF020, 256 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF020B, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF032B, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF040, 512 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF040B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF040B.REMS, 512 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF064C, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF512(A), 64 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25WF010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF020A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF040B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF016B(A), 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF032B(A), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF064B(A), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ST M95M02, 256 kB: probe_spi_st95: id1 0xff, id2 0xffff
Probing for Sanyo LE25FU106B, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU206, 256 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU206A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FU406B, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU406C/LE25U40CMC, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW106, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW203A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW403A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW406A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW418A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW806, 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW808, 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Spansion S25FL004A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL008A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL016A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL032A/P, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL064A/P, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL116K/S25FL216K, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL127S-256kB, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL127S-64kB, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128L, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128P......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128P......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S_UL Uniform 128 kB Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL128S_US Uniform 64 kB Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL129P......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL129P......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL132K, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL164K, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL204K, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL208K, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL256L, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL256S Large Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL256S Small Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL256S......0, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL512S, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FS128S Large Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FS128S Small Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Winbond W25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.V, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.V..M, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.W, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.JW.DTR, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16JV_M, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16.V, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16.W, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q20.W, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256FV, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JV_Q, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JV_M, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JW, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25R512NW/W74M51NW, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JW_DTR, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32BV/W25Q32CV/W25Q32DV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32FV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JV_M, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32BW/W25Q32CW/W25Q32DW, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32FW, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JW...Q, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JW...M, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40.V, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40BW, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40EW, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q512JV, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q512NW-IM, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64BV/W25Q64CV/W25Q64FV, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JV-.Q, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JV-.M, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64.W, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JW...M, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80.V, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80BW, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80EW, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH80B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU80B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH16C/XM25QH16D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU16C, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH32C/XM25QH32D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU32C, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH64C/XM25QH64D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU64C/XM25LU64C, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH128C/XM25QH128D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU128C/XM25QU128D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH256C/XM25QH256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU256C/XM25QU256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25RU256C, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH512C/XM25QH512D, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU512C/XM25QU512D, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F02E, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F64B, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F128B, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25D20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25D40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25LQ128, 16384 kB: compare_id: id1 0xc2, id2 0x18
Probing for Unknown SFDP-capable chip, 0 kB: Parsing JEDEC flash parameter table... Flash chip size is bigger than what 3-Byte addressing can access.
Support for SFDP Page with ID 0xc2 not implemented, skipping it.
Support for SFDP Page with ID 0x84 not implemented, skipping it.
Probing for AMIC unknown AMIC SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel unknown Atmel SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon unknown Eon SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix unknown Macronix SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC unknown PMC SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST unknown SST SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ST unknown ST SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo unknown Sanyo SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond unknown Winbond (ex Nexcom) SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Generic unknown SPI chip (RDID), 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Generic unknown SPI chip (REMS), 0 kB: compare_id: id1 0xc2, id2 0x18
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI).
This chip may contain one-time programmable memory. flashrom cannot read
and may never be able to write it, hence it may not be able to completely
clone the contents of this chip (see man page for details).
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
Reading flash... read_flash:  region (00000000..0x1ffffff) is readable, reading range (00000000..0x1ffffff).
done.

________________________________________________________
Executed in  252.46 secs      fish           external
   usr time    8.85 millis  641.00 micros    8.21 millis
   sys time   24.84 millis  204.00 micros   24.64 millis


~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2) took 4m12s
```
# Verify
```
~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2) took 4m12s
🐟 ❯ sha1sum backup.bin backup.bin2                                                              (base)
5516522041d9fb89c92d586c87ba1a2dcab1676a  backup.bin
5516522041d9fb89c92d586c87ba1a2dcab1676a  backup.bin2
```

```
~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ du -sh *                                                                                    (base)
32M     backup.bin
32M     backup.bin2
16M     f31-flash_G.rom
16M     r03-f33-flash_G.rom
40K     README.md

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ ls -l *                                                                                     (base)
-rw-r--r-- 1 lhl  lhl     40892 Jan 14 17:47 README.md
-rw-r--r-- 1 root root 33554432 Jan 14 17:40 backup.bin
-rw-r--r-- 1 root root 33554432 Jan 14 17:44 backup.bin2
-rw-r--r-- 1 lhl  lhl  16777216 Jan 14 17:47 f31-flash_G.rom
-rw-r--r-- 1 lhl  lhl  16777216 Jan 14 17:48 r03-f33-flash_G.rom

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ more ~/Downloads/gigabyte/bios-f31/                                                         (base)
/home/lhl/Downloads/gigabyte/bios-f31/ is a directory

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ ls ~/Downloads/gigabyte/bios-f31/                                                           (base)
RBU                        Relnotes_MZ33-AR0_F31_Genoa.pdf  Tool   f2BIOS.nsh
Relnotes_MZ33-AR0_F31.pdf  SPI_UPD                          f.nsh  flash_G.rom

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ ls ~/Downloads/gigabyte/bios-f31/f.nsh                                                      (base)
/home/lhl/Downloads/gigabyte/bios-f31/f.nsh

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ more ~/Downloads/gigabyte/bios-f31/f.nsh                                                    (base)
#for Boot image
SPI_UPD\AfuEfix64.efi flash_G.rom /p /b /n /k /l /RLC:E

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ more ~/Downloads/gigabyte/bios-f31/f2BIOS.nsh                                               (base)
ECHO -off
ECHO "================= Update Both 1st + 2nd BIOS Region ================="

f.nsh

if not %lasterror% == 0 then
if not %lasterror% == 0x64 then
ECHO "===================== Update 1st BIOS FAIL ====================="
goto EXIT1
endif
endif

SPI_UPD\AfuEfix64.efi /OEMCMD:2B

ECHO "================ Update Both 1st + 2nd BIOS Complete ================"

:EXIT1

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ time sudo flashrom -p ch341a_spi -w f31-flash_G.rom --layout backup.bin --image complete_flash:0
Enter Password or Place finger on fingerprint reader:
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

Error parsing layout file. Offending string: ""

________________________________________________________
Executed in    2.80 secs      fish           external
   usr time    8.77 millis    0.00 micros    8.77 millis
   sys time   25.21 millis  935.00 micros   24.28 millis


~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2) took 2s
🐟 ❯ sudo flashrom -p ch341a_spi -w f31-flash_G.rom -V                                           (base)
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

flashrom was built with GCC 14.2.1 20240910, little endian
Command line (5 args): flashrom -p ch341a_spi -w f31-flash_G.rom -V
Initializing ch341a_spi programmer
Device revision is 3.0.4
The following protocols are supported: SPI.
Probing for AMIC A25L010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L032, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L05PT, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L05PU, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L10PT, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L10PU, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L16PT, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L16PU, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L20PT, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L20PU, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L40PT, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L40PU, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L80P, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ032/A25LQ32A, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF011, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF021, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF021A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF041A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF081A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF321, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF321A, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF641(A), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DL081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DL161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DQ161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25F1024(A), 128 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F2048, 256 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F4096, 512 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512, 64 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512A, 64 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512B, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25FS010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25FS040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF041, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF321, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SL128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF041, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF081A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF161A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26F004, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45CS1282, 16896 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB011D, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB021D, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB041D, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB081D, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB161D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321C, 4224 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB642D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25D16A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25D80A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25Q64AS, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25Q128AS, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESMT F25L008A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESMT F25L32PA, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B05T, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B10T, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B16T, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B20T, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B32T, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B40T, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B64T, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B80T, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q32(A/B), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q80(A), 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH32B, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH64A, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F005, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F01, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F02(A), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F04(A), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q04, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q08, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25B128B/GD25Q128B, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF128E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ128E/GD25LB128E/GD25LR128E/GD25LQ128D/GD25LQ128C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ255E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ64(B), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB256E/GD25LR256E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB256F/GD25LR256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB512MF/GD25LR512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB512ME/GD25LR512ME, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q128E/GD25B128E/GD25R128E/GD25Q127C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q128C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q16(B), 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q20(B), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q256E/GD25B256E/GD25R256E/GD25Q256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25B512MF/GD25R512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q32(B), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q40(B), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q64(B), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q80(B), 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25T80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ16C, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ21B, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ40C, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ41B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ80C, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F64F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F128F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25WQ80E, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP064, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LQ016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP032, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP064, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WQ040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F160S33B8, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F160S33T8, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F320S33B8, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F320S33T8, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F640S33B8, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F640S33T8, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L12854, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L1654, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L3254, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L6454, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1005(C)/MX25L1006E, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12805D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12833F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12835F/MX25L12873F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12845E/MX25L12865E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12850F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V16066, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605A/MX25L1606E/MX25L1608E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605D/MX25L1608D/MX25L1673E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1635D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1633E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1635E/MX25L1636E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L2005(C)/MX25L2006E, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L25635F/MX25L25645G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Added layout entry 00000000 - 01ffffff named complete flash
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
Chip status register is 0x40.
Chip status register: Status Register Write Disable (SRWD, SRP, ...) is not set
Chip status register: Bit 6 is set
Chip status register: Block Protect 3 (BP3) is not set
Chip status register: Block Protect 2 (BP2) is not set
Chip status register: Block Protect 1 (BP1) is not set
Chip status register: Block Protect 0 (BP0) is not set
Chip status register: Write Enable Latch (WEL) is not set
Chip status register: Write In Progress (WIP/BUSY) is not set
Probing for Macronix MX25L3205(A), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3205D/MX25L3208D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3206E/MX25L3208E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3273F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3239E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3235D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3233F/MX25L3273E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3255E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L4005(A/C)/MX25L4006E, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L512(E)/MX25V512(C), 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L5121E, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6405, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6405D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6406E/MX25L6408E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6436E/MX25L6445E/MX25L6465E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6473E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6473F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6495F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L8005/MX25L8006E/MX25L8008E/MX25V8005, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R1635F, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R2035F, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R3235F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R4035F, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R6435F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R8035F, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V4035F, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V8035F, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V1635F, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U12835F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U1635E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25635F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25643G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25645G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U3235E/F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U51245G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U6435E/F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U8032E, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX66L51235F/MX25L51245G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX66L1G45G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX77L25650F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX77U51250F, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P05, 64 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P05-A, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P10, 128 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P10-A, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P20-old, 256 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P40-old, 512 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q00A..1G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q00A..3G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q032..1E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q032..3E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q064..1E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q064..3E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q128..1E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q128..3E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q256..1E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q256..3E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q512..1G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q512..3G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL01G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU01G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL02G, 262144 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU02G, 262144 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL512, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU512, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD010(C), 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD020(C), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD040(C), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD256C, 32 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD512(C), 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ032C, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV010, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for PMC Pm25LV010A, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV016B, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV512(A), 64 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for PUYA P25Q06H, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PUYA P25Q11H, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PUYA P25Q21H, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25LF020A, 256 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25LF040A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for SST SST25LF080(A), 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for SST SST25VF010(A), 128 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF016B, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF020, 256 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF020B, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF032B, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF040, 512 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF040B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF040B.REMS, 512 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF064C, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF512(A), 64 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25WF010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF020A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF040B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF016B(A), 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF032B(A), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF064B(A), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ST M95M02, 256 kB: probe_spi_st95: id1 0xff, id2 0xffff
Probing for Sanyo LE25FU106B, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU206, 256 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU206A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FU406B, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU406C/LE25U40CMC, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW106, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW203A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW403A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW406A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW418A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW806, 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW808, 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Spansion S25FL004A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL008A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL016A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL032A/P, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL064A/P, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL116K/S25FL216K, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL127S-256kB, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL127S-64kB, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128L, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128P......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128P......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S_UL Uniform 128 kB Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL128S_US Uniform 64 kB Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL129P......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL129P......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL132K, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL164K, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL204K, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL208K, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL256L, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL256S Large Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL256S Small Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL256S......0, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL512S, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FS128S Large Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FS128S Small Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Winbond W25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.V, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.V..M, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.W, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.JW.DTR, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16JV_M, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16.V, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16.W, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q20.W, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256FV, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JV_Q, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JV_M, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JW, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25R512NW/W74M51NW, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JW_DTR, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32BV/W25Q32CV/W25Q32DV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32FV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JV_M, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32BW/W25Q32CW/W25Q32DW, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32FW, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JW...Q, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JW...M, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40.V, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40BW, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40EW, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q512JV, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q512NW-IM, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64BV/W25Q64CV/W25Q64FV, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JV-.Q, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JV-.M, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64.W, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JW...M, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80.V, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80BW, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80EW, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH80B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU80B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH16C/XM25QH16D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU16C, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH32C/XM25QH32D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU32C, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH64C/XM25QH64D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU64C/XM25LU64C, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH128C/XM25QH128D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU128C/XM25QU128D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH256C/XM25QH256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU256C/XM25QU256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25RU256C, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH512C/XM25QH512D, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU512C/XM25QU512D, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F02E, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F64B, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F128B, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25D20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25D40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25LQ128, 16384 kB: compare_id: id1 0xc2, id2 0x18
Probing for Unknown SFDP-capable chip, 0 kB: Parsing JEDEC flash parameter table... Flash chip size is bigger than what 3-Byte addressing can access.
Support for SFDP Page with ID 0xc2 not implemented, skipping it.
Support for SFDP Page with ID 0x84 not implemented, skipping it.
Probing for AMIC unknown AMIC SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel unknown Atmel SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon unknown Eon SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix unknown Macronix SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC unknown PMC SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST unknown SST SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ST unknown ST SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo unknown Sanyo SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond unknown Winbond (ex Nexcom) SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Generic unknown SPI chip (RDID), 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Generic unknown SPI chip (REMS), 0 kB: compare_id: id1 0xc2, id2 0x18
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI).
This chip may contain one-time programmable memory. flashrom cannot read
and may never be able to write it, hence it may not be able to completely
clone the contents of this chip (see man page for details).
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
Error: Image size (16777216 B) doesn't match the expected size (33554432 B)!

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ echo '00000000:00ffffff main' > bios.layout                                                 (base)

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ time sudo flashrom -p ch341a_spi -l bios.layout -i main -w f31-flash_G.rom                  (base)
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

Using region: "main".
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
Error: Image size (16777216 B) doesn't match the expected size (33554432 B)!

________________________________________________________
Executed in  167.02 millis    fish           external
   usr time    3.47 millis  479.00 micros    2.99 millis
   sys time   26.84 millis  159.00 micros   26.68 millis


~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ dd if=/dev/zero of=flash_32MB.bin bs=32M count=1                                            (base)
1+0 records in
1+0 records out
33554432 bytes (34 MB, 32 MiB) copied, 0.0366836 s, 915 MB/s

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ dd if=f31-flash_G.rom of=flash_32MB.bin bs=1M conv=notrunc                                  (base)
16+0 records in
16+0 records out
16777216 bytes (17 MB, 16 MiB) copied, 0.013719 s, 1.2 GB/s

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ dd if=backup.bin of=flash_32MB.bin bs=1M skip=16 seek=16 count=16 conv=notrunc              (base)
16+0 records in
16+0 records out
16777216 bytes (17 MB, 16 MiB) copied, 0.0171625 s, 978 MB/s

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ ls -l flash_32MB.bin                                                                        (base)
-rw-r--r-- 1 lhl lhl 33554432 Jan 14 17:58 flash_32MB.bin

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ sha1sum flash_32MB.bin                                                                      (base)
2c89975e38bdf98c0330154be1ba91bfc05cfb2a  flash_32MB.bin

~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2)
🐟 ❯ sudo flashrom -p ch341a_spi -w flash_32MB.bin                                               (base)
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
Reading old flash chip contents... done.
Updating flash chip contents... Erase/write done from 0 to 1ffffff
Verifying flash... VERIFIED.
```

# Verify Write
```
🐟 ❯ time sudo flashrom -p ch341a_spi -r new-32mb-dump.bin -V                                    (base)
Enter Password or Place finger on fingerprint reader:
flashrom v1.5.1 (git:v1.5.1) on Linux 6.12.8-arch1-1 (x86_64)
flashrom is free software, get the source code at https://flashrom.org

flashrom was built with GCC 14.2.1 20240910, little endian
Command line (5 args): flashrom -p ch341a_spi -r new-32mb-dump.bin -V
Initializing ch341a_spi programmer
Device revision is 3.0.4
The following protocols are supported: SPI.
Probing for AMIC A25L010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L032, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L05PT, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L05PU, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L10PT, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L10PU, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L16PT, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L16PU, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L20PT, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L20PU, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L40PT, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L40PU, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25L80P, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ032/A25LQ32A, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for AMIC A25LQ64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF011, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF021, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF021A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF041A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF081A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF321, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF321A, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DF641(A), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DL081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DL161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25DQ161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25F1024(A), 128 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F2048, 256 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F4096, 512 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512, 64 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512A, 64 kB: probe_spi_at25f: id1 0x20, id2 0x20
Probing for Atmel AT25F512B, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25FS010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25FS040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF041, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF081, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SF321, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT25SL128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF041, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF081A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF161, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26DF161A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT26F004, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45CS1282, 16896 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB011D, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB021D, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB041D, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB081D, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB161D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321C, 4224 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB321E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel AT45DB642D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25D16A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25D80A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25Q64AS, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Boya/BoHong Microelectronics B.25Q128AS, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESI ES25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESMT F25L008A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ESMT F25L32PA, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B05T, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B10T, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B16T, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B20T, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B32T, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B40T, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B64T, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25B80T, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25F80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q32(A/B), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25Q80(A), 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH32B, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25QH64A, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon EN25S80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F005, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F01, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F02(A), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25F04(A), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q04, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q08, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Fudan FM25Q128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25B128B/GD25Q128B, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF128E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LF512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ128E/GD25LB128E/GD25LR128E/GD25LQ128D/GD25LQ128C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ255E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ64(B), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LQ80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB256E/GD25LR256E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB256F/GD25LR256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB512MF/GD25LR512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25LB512ME/GD25LR512ME, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q128E/GD25B128E/GD25R128E/GD25Q127C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q128C, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q16(B), 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q20(B), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q256E/GD25B256E/GD25R256E/GD25Q256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25B512MF/GD25R512MF, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q32(B), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q40(B), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q64(B), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25Q80(B), 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25T80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ16C, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ21B, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ40C, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ41B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25VQ80C, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F64F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F128F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25F256F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for GigaDevice GD25WQ80E, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP064, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LP256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25LQ016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP032, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP064, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WP256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ISSI IS25WQ040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F160S33B8, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F160S33T8, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F320S33B8, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F320S33T8, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F640S33B8, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Intel 25F640S33T8, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L12854, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L1654, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L3254, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX23L6454, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1005(C)/MX25L1006E, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12805D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12833F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12835F/MX25L12873F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12845E/MX25L12865E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L12850F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V16066, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605A/MX25L1606E/MX25L1608E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1605D/MX25L1608D/MX25L1673E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1635D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1633E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L1635E/MX25L1636E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L2005(C)/MX25L2006E, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L25635F/MX25L25645G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Added layout entry 00000000 - 01ffffff named complete flash
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI) on ch341a_spi.
Chip status register is 0x40.
Chip status register: Status Register Write Disable (SRWD, SRP, ...) is not set
Chip status register: Bit 6 is set
Chip status register: Block Protect 3 (BP3) is not set
Chip status register: Block Protect 2 (BP2) is not set
Chip status register: Block Protect 1 (BP1) is not set
Chip status register: Block Protect 0 (BP0) is not set
Chip status register: Write Enable Latch (WEL) is not set
Chip status register: Write In Progress (WIP/BUSY) is not set
Probing for Macronix MX25L3205(A), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3205D/MX25L3208D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3206E/MX25L3208E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3273F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3239E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3235D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3233F/MX25L3273E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L3255E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L4005(A/C)/MX25L4006E, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L512(E)/MX25V512(C), 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L5121E, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6405, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6405D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6406E/MX25L6408E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6436E/MX25L6445E/MX25L6465E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6473E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6473F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L6495F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25L8005/MX25L8006E/MX25L8008E/MX25V8005, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R1635F, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R2035F, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R3235F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R4035F, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R6435F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25R8035F, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V4035F, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V8035F, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25V1635F, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U12835F, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U1635E, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25635F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25643G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U25645G, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U3235E/F, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U51245G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U6435E/F, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX25U8032E, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX66L51235F/MX25L51245G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX66L1G45G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX77L25650F, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix MX77U51250F, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P05, 64 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P05-A, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P10, 128 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P10-A, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P20-old, 256 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P40-old, 512 kB: Ignoring RES in favour of RDID.
Probing for Micron/Numonyx/ST M25P64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PE80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M25PX80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST M45PE80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q00A..1G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q00A..3G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q032..1E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q032..3E, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q064..1E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q064..3E, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q128..1E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q128..3E, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q256..1E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q256..3E, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q512..1G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron/Numonyx/ST N25Q512..3G, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL01G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU01G, 131072 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL02G, 262144 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU02G, 262144 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL128, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU256, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QL512, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Micron MT25QU512, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Nantronics N25S80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD010(C), 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD020(C), 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD040(C), 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD256C, 32 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LD512(C), 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ016, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ032C, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LQ080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV010, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for PMC Pm25LV010A, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV016B, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC Pm25LV512(A), 64 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for PUYA P25Q06H, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PUYA P25Q11H, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PUYA P25Q21H, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25LF020A, 256 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25LF040A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for SST SST25LF080(A), 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for SST SST25VF010(A), 128 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF016B, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF020, 256 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF020B, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF032B, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF040, 512 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF040B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF040B.REMS, 512 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25VF064C, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25VF512(A), 64 kB: compare_id: id1 0xc2, id2 0x18
Probing for SST SST25WF010, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF020, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF020A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF040, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF040B, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF080, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF080B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST25WF512, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF016B(A), 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF032B(A), 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST SST26VF064B(A), 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ST M95M02, 256 kB: probe_spi_st95: id1 0xff, id2 0xffff
Probing for Sanyo LE25FU106B, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU206, 256 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU206A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FU406B, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FU406C/LE25U40CMC, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW106, 128 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW203A, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW403A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo LE25FW406A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW418A, 512 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW806, 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Sanyo LE25FW808, 1024 kB: probe_spi_res2: id1 0x18, id2 0x18
Probing for Spansion S25FL004A, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL008A, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL016A, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL032A/P, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL064A/P, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL116K/S25FL216K, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL127S-256kB, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL127S-64kB, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128L, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128P......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128P......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL128S_UL Uniform 128 kB Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL128S_US Uniform 64 kB Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL129P......0, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL129P......1, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL132K, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL164K, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL204K, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL208K, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL256L, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL256S Large Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL256S Small Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FL256S......0, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FL512S, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Spansion S25FS128S Large Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Spansion S25FS128S Small Sectors, 16384 kB: Read id bytes:  0xc2 0x20 0x19 0xc2 0x20 0x19.
Probing for Winbond W25P16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25P32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25P80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.V, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.V..M, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.W, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q128.JW.DTR, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16JV_M, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16.V, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q16.W, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q20.W, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256FV, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JV_Q, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JV_M, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JW, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25R512NW/W74M51NW, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q256JW_DTR, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32BV/W25Q32CV/W25Q32DV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32FV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JV_M, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JV, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32BW/W25Q32CW/W25Q32DW, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32FW, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JW...Q, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q32JW...M, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40.V, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40BW, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q40EW, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q512JV, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q512NW-IM, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64BV/W25Q64CV/W25Q64FV, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JV-.Q, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JV-.M, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64.W, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q64JW...M, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80.V, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80BW, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25Q80EW, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X05, 64 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X10, 128 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X16, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X32, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X64, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond W25X80, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH80B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU80B, 1024 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH16C/XM25QH16D, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU16C, 2048 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH32C/XM25QH32D, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU32C, 4096 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH64C/XM25QH64D, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU64C/XM25LU64C, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH128A, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH128C/XM25QH128D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU128C/XM25QU128D, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH256C/XM25QH256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU256C/XM25QU256D, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25RU256C, 32768 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QH512C/XM25QH512D, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XMC XM25QU512C/XM25QU512D, 65536 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F02E, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F64B, 8192 kB: compare_id: id1 0xc2, id2 0x2019
Probing for XTX Technology Limited XT25F128B, 16384 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25D20, 256 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25D40, 512 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Zetta Device ZD25LQ128, 16384 kB: compare_id: id1 0xc2, id2 0x18
Probing for Unknown SFDP-capable chip, 0 kB: Parsing JEDEC flash parameter table... Flash chip size is bigger than what 3-Byte addressing can access.
Support for SFDP Page with ID 0xc2 not implemented, skipping it.
Support for SFDP Page with ID 0x84 not implemented, skipping it.
Probing for AMIC unknown AMIC SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Atmel unknown Atmel SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Eon unknown Eon SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Macronix unknown Macronix SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for PMC unknown PMC SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for SST unknown SST SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for ST unknown ST SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Sanyo unknown Sanyo SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Winbond unknown Winbond (ex Nexcom) SPI chip, 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Generic unknown SPI chip (RDID), 0 kB: compare_id: id1 0xc2, id2 0x2019
Probing for Generic unknown SPI chip (REMS), 0 kB: compare_id: id1 0xc2, id2 0x18
Found Macronix flash chip "MX25L25635F/MX25L25645G" (32768 kB, SPI).
This chip may contain one-time programmable memory. flashrom cannot read
and may never be able to write it, hence it may not be able to completely
clone the contents of this chip (see man page for details).
===
This flash part has status UNTESTED for operations: WP
The test status of this chip may have been updated in the latest development
version of flashrom. If you are running the latest development version,
please email a report to flashrom@flashrom.org if any of the above operations
work correctly for you with this flash chip. Please include the flashrom log
file for all operations you tested (see the man page for details), and mention
which mainboard or programmer you tested in the subject line.
You can also try to follow the instructions here:
https://www.flashrom.org/contrib_howtos/how_to_mark_chip_tested.html
Thanks for your help!
Reading flash... read_flash:  region (00000000..0x1ffffff) is readable, reading range (00000000..0x1ffffff).
done.

________________________________________________________
Executed in  255.79 secs      fish           external
   usr time   25.87 millis  386.00 micros   25.48 millis
   sys time   10.61 millis  131.00 micros   10.48 millis


~/Desktop/gigabyte-bios-recovery on ☁️  (us-west-2) took 4m15s
🐟 ❯ sha1sum flash_32MB.bin new-32mb-dump.bin                                                    (base)
2c89975e38bdf98c0330154be1ba91bfc05cfb2a  flash_32MB.bin
2c89975e38bdf98c0330154be1ba91bfc05cfb2a  new-32mb-dump.bin
```
