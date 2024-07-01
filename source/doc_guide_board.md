# Instructions for the use board

**AXera_Pi Zero** adds 4G wireless communications board (referred to as: expansion board), supports 4G/WIFI/SD card.<br />
![](./media/board/board_1.png)

<font size="5">Using different modes, the antenna installation position is also different. The specific connection position is shown in the figure.</font><br />
![](./media/board/board_2.jpg)

![](./media/board/board_3.jpg)

## use SD card

1.After inserting the SD card, enter the terminal to see if there is a SD card partition.<br />
![](./media/board/SD/sd_1.jpg)

2.Format the SD card.<br />
![](./media/board/SD/sd_2.png)

3.Create a folder that needs to be placed.<br />
![](./media/board/SD/sd_3.jpg)

4.Mount SD card to the created folder.<br />
![](./media/board/SD/sd_4.png)

5.Enter the command to see if it is successful.<br />
![](./media/board/SD/sd_5.jpg)

6.If you need to mount it to other positions, first uninstall the original mount position, confirm whether the uninstallation is successful in step 5, and then start the operation from step 1.<br />
![](./media/board/SD/sd_6.png)

## Switch 4G mode

<font color="red"><b>When switching the 4G/WIFI mode, you need to enter through the network cable/serial line. At this time, the Type-C line is only for power supply function. When the jumper hat is switched, it needs to be performed in the state of power off.</font></b>

1.Connect to network cables and Type-C cable，<a href="https://axera-pi-zero-docs-cn.readthedocs.io/zh-cn/latest/doc_guide_faq.html">Configuration device IP</a>.

2.Disgle the Type-C line and place the jumper hat of the motherboard on the WIFI side. (When downloading the burning, you need to place the jump cap on the Typec side)<br />
![](./media/board/board_4.jpg)

3.Place the jumper hat of the extended board to the LTE end, insert 4G card, and switch to 4G mode.<br />
![](./media/board/4G/4g_1.jpg)

4.Connect the Type-C line, open the Putty, and enter the device terminal through the configured IP.<br />
![](./media/board/4G/4g_2.jpg)

5.Switch to OTG.<br />
![](./media/board/4G/4g_3.jpg)

6.Enter the command. If the following pictures are shown, the OTG switch is successful.<br />
![](./media/board/4G/4g_4.jpg)

![](./media/board/4G/4g_5.jpg)

7.Dial with dialing tools (no need to stop, return to the next step).<br />
![](./media/board/4G/4g_6.png)

8.Dial with dialing tools (no need to stop, return to the next step).<br />
![](./media/board/4G/4g_7.jpg)

## Switch WiFi mode

1.Same as the first and 2nd points of switching 4G mode.<br />

2.Switch the jumper hat of the expansion board to the WiFi end and switch to the WIFI mode.<br />
![](./media/board/wifi/wifi_1.jpg)

3.Same as the 4th and 5th points of switching 4G mode.<br />

4.Manually pull up the wifi GPIO port.<br />
![](./media/board/wifi/wifi_7.png)

5.Download the WIFI driver and wait for a while.<br />
![](./media/board/wifi/wifi_2.jpg)

6.Enter the command. If the following pictures appear, the WiFi driver download is successful.<br />
![](./media/board/wifi/wifi_3.png)

![](./media/board/wifi/wifi_4.jpg)

7.Manually pull up the WiFi network interface.<br />
![](./media/board/wifi/wifi_5.jpg)

8.Confirm whether the WIFI network interface is successfully pulled up through the command.<br />
![](./media/board/wifi/wifi_6.jpg)

<font color="red"><b>When choosing a WiFi mode, only one of them can be selected, and two modes are not allowed to exist simultaneously.</font></b>

### WIFI's AP mode

1.Configure the hostapd.conf file of wifi. (WiFi name and password can be configured by yourself).<br />
![](./media/board/wifi/AP/ap_1.jpg)

2.Start hostapd. (With this print, it means successful start).<br />
![](./media/board/wifi/AP/ap_2.png)

3.Configure the udhcpd.conf file. (The network segment can be configured by itself).<br />
![](./media/board/wifi/AP/ap_3.jpg) 

4.Allocate the IP address for wlan0, the default is the gateway address.<br />
![](./media/board/wifi/AP/ap_4.jpg)

5.Start UDHCPD.<br />
![](./media/board/wifi/AP/ap_5.jpg)

6.The configured WiFi is connected by the mobile phone to verify whether it is successful.<br />


### WIFI's STA mode

1.Configure the wpa_supplicant.conf file.<br />
![](./media/board/wifi/STA/sta_1.jpg)

2.Start the wpa_supplicant service in the background.<br />
![](./media/board/wifi/STA/sta_2.png)

3.Scan and obtain WiFi hotspots around the peripheral, confirm that the WiFi hotspot that needs to be connected is among them.<br />
![](./media/board/wifi/STA/sta_3.jpg)

4.Automatically obtain the IP address assigned by WiFi hot spots through commands.<br />
![](./media/board/wifi/STA/sta_4.jpg)

5.Verify whether the device can access the Internet.<br />
![](./media/board/wifi/STA/sta_5.jpg)
