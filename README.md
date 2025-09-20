# To install PX4
You need to set RC_CRSF_PRT_CFG parameter to the serial that you’re using. BUT You can’t use prebuilt PX4 release (or main) firmware for this, as it depends on PX4 modules crsf_rc. To add RC_CRSF_PRT_CFG to parameter list you need to create your own PX4 build

    Get PX4 repo and needed items for build (Follow this guide - Building PX4 Software | PX4 User Guide), i recommend using ubuntu or WSL ubuntu
    Build firmware for pixhawk 2.4.8, to do it run “make px4_fmu-v3_default”
    Change config by command “make px4_fmu-v3_default boardconfig”.
    a)In the PX4 board config tool, navigate to the drivers submenu, then scroll down to highlight rc_input.
    b) Use the enter key to remove the * from rc_input checkbox.
    c) Scroll to highlight the RC submenu, then press enter to open it.
    d) Scroll to highlight crsf_rc and press enter to enable it.
    e) Save and exit the PX4 board config tool.
    Run build again “make px4_fmu-v3_default”
    Get your build in “\build” folder and install it to your pixhawk
    Set RC_CRSF_PRT_CFG to serail that you are using, in my case Serial 4/5 port
