# Software for the M4 core of the i.MX7 ULP uCOM
1. Clone this repository
2. Download the SDK (SDK_2.6.0_EVK-MCIMX7ULP.zip) from [Welcome | MCUXpresso SDK Builder](https://mcuxpresso.nxp.com/en/welcome)
3. Unpack the SDK into the cloned repository
4. Apply the patches in numerical order:

    `git apply 0001-bd70528-Add-driver.patch`
    
	`git apply 0002-power_mode_switch-Add-application-for-Rohm-PMIC.patch`
    
	`git apply 0003-ea_ucom.patch`
	
# Compile
1. Double-click boards\evkmcimx7ulp\demo_apps\rohm_power_mode_switch\iar\power_mode_switch.eww
2. Build
3. Copy boards\evkmcimx7ulp\demo_apps\rohm_power_mode_switch\iar\debug\sdk20-app.bin to tools\imgutil\evkmcimx7ulp\
4. Run `..\bin\imgutil.exe --combine base_addr=0x1FFD0000 ivt_offset=0x1000 config_offset=0x400 config_file=qcb.bin app_offset=0x2000 app_file=sdk20-app.bin ofile=sdk20-app.img`
5. Copy sdk20-app.img to the folder with uuu to flash it
