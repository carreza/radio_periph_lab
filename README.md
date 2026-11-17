# radio_periph_lab
EN.525.742, radio peripheral laboratory

edit of https://github.com/dougwen/radio_periph_lab

## Setting up project
- run "make_project" (requires Vivado 2025.2), path length must not exceed 260 characters on Windows
- connect Zybo Z7 to network using ethernet (optionally, through serial as well)
- copy the following files to /home/student/ on the board
> - /radio_periph_lab/vivado/radio_periph_lab.runs/impl_1/design_1_wrapper.bit.bin
> - /radio_periph_lab/src/linux_software/test_radio.c

## On Zybo Z7
### Flashing FPGA
```
sudo -i
cd /home/student/
fpgautil -b design_1_wrapper.bit.bin
```

### Configuring Codec
Requires the Linux SD card image provided in module 9.
```
cd /run/media/mmcblk0p1/
./config_codec.sh
```

Running Testfile
```
cd /home/student/
gcc test_radio.c -o test_radio
./test_radio 
```
