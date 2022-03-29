#Download and build
cd /tmp
git clone https://github.com/gnetanel/rtl8812au.git gnab_rtl8812au
cd gnab_rtl8812au
make
sudo insmod 8812au.ko

# permanently add
cd /tmp
sudo cp -R gnab_rtl8812au /usr/src/8812au-4.2.2
sudo dkms add -m 8812au -v 4.2.2
sudo dkms build -m 8812au -v 4.2.2
sudo dkms install -m 8812au -v 4.2.20
