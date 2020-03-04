# Software for the M4 core of the i.MX7 ULP uCOM
1. Clone this repository
2. Download the SDK (SDK_2.7.0_EVK-MCIMX7ULP.zip) from [Welcome | MCUXpresso SDK Builder](https://mcuxpresso.nxp.com/en/welcome)
3. Unpack the SDK into the cloned repository
4. Apply the patch:

    `git apply 0001-ea_ucom.patch`
	
# Compile
1. Double-click boards\evkmcimx7ulp\demo_apps\power_mode_switch\iar\power_mode_switch.eww
2. Build
3. Copy boards\evkmcimx7ulp\demo_apps\power_mode_switch\iar\debug\sdk20-app.bin to tools\imgutil\evkmcimx7ulp\
4. Open a Command Prompt and go to tools\imgutil\evkmcimx7ulp\
5. Run `..\bin\imgutil.exe --combine base_addr=0x1FFD0000 ivt_offset=0x1000 config_offset=0x400 config_file=qcb.bin app_offset=0x2000 app_file=sdk20-app.bin ofile=sdk20-app.img`
6. Copy sdk20-app.img to the folder with uuu to flash it
