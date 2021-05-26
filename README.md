# About

Check NAS QNAP from Icinga2 or similar monitoring software.

# Usage: Icinga2

Enable SNMP on QNAP NAS appliance and use this script with Icinga2.

Copy the command_qnap_health.conf into the configuration path of Icinga2.

# Usage: Nagios

Enable SNMP on QNAP NAS appliance, community name "public".

Add this at the end of your "/usr/local/nagios/etc/objects/commands.cfg":

```
##########
## QNAP	##
##########
define command{
	command_name 	qnap_health
	command_line 	$USER1$/qnap_health -H $HOSTADDRESS$ -C public -p $ARG1$ -w $ARG2$ -c $ARG3$
}
```

# Contributing

Please feel free to fork and collaborate on this little but useful project.

# Parts of script to improve

- Power unit check - (let me know if on your device work)
- Rewrite some code for better readability

# Test

This script was tested with:
- QNAP model TS-853U-RP (with 4 disk)
- QNAP model TS-859U+ (by Omar S. Ramirez thanks for your help)
- QNAP model TS-212 and TS-231P (by github user mir07 Michael Rasmussen)
- QNAP Model TS-EC1280U, Firmware 4.2.2 (Thanks to AndresCidoncha)
- QNAP Model TS-459 Pro+, Firmware 4.2.6, Max HD number 4, No. Volume 1
- QNAP Model TS-1263U-RP, Firmware 4.3.3, Max HD number 12, No. Volume 1
- QNAP Model TS-EC1680U, Firmware 4.3.6, Max HD number 16
- QNAP Model TS-EC2480U, Firmware 4.3.6, Max HD number 24
- QNAP Model TS-431P2, Firmware 4.4.1
