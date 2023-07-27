## Openwrt 19.07.8 image for TP-Link MR200v4

Install via TFTP. Rename openwrt_19.07.8_tp_recovery.bin to tp_recovery.bin. Copy tp_recovery.bin to TFTP directory.\
TFTP server IP address 192.168.0.225 netmask 255.255.255.0. Turn off all firewalls.

1. Power off router
2. Connect router to your TFTP server
3. Press WPS/RESET while you power on router, keep pressed for 10s
4. TFTP loading should now start
5. Wait until router has restarted
6. Log in with browser to 192.168.1.1

\
After succcess full installation you need to add your wwan interface.

1. Network - interfaces
2. Add new interface
3. Name: wwan\
   Protocol: QMI Cellular\
   -Create interface
4. General Settings -\
   Modem device: /dev/cdc-wdm0\
   Add your APN settings
5. Advanced Settings - Modem timeout: 20
6. Firewall Settings - Create / Assign firewall-zon\
   -Save\
   -Save & Apply
7. Install mr200v4/lte-modem-fix-19.07.8/uqmi_2022-11-29-0.10_mipsel_24kc.ipk and from System -> Software -> Upload, then restart the device.
