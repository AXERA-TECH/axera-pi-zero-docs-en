# Application Development Demo

## Usage of FRTDemo

1. Use Type-C to connect Aixinpai Zero to the computer. There are two ways to enter the terminal.
<p style="text-indent:2em;">a. Enter directly through the serial port</p>
<p style="text-indent:2em;">b. Via <a href="https://axera-pi-zero-docs-cn.readthedocs.io/zh-cn/latest/doc_guide_faq.html"> Modify the IP</a> and use a network cable to connect the device to the computer</p>

2. Open putty, enter the serial port/IP corresponding to the device, and click Open<br />

3. After entering, enter the user password and enter the terminal (the password will not be displayed)<br />
Username: root<br />
Password: 123456<br />
![](./media/FAQ/FAQ_3.jpg)

4. Enter the command to enter FRTDemo<br />
![](./media/demo/demo_1.jpg)

5. Enter the command to start Demo<br />
![](./media/demo/demo_2.jpg)

6. Open the web page and enter the URL in the running content into the URL box
![](./media/demo/demo_3.jpg)

7. Log in to the webpage corresponding to the Demo to preview immediately.
![](./media/demo/demo_4.jpg)

If you need the FRTDemo source code, please click <a href="https://github.com/AXERA-TECH/ax620q_bsp_sdk">here</a> to view<br />
<br />
<br />

## NFS mount

1. Click <a href="https://pan.baidu.com/s/1ZhK5TAt4H6BPRn4bDA1oXA">this link</a> to download the nfs server tool<br />
Extraction code: Zero<br />

2. Replace the exports file in the installation package with the path where nfs is located.
![](./media/nfs/nfs_1.jpg)

4. Open the nfs server on the desktop, click Output, click Edit output table file, fill in the file corresponding to the IP address of the device and the directory to be shared, and click Restart the server<br />
![](./media/nfs/nfs_3.jpg)

5. Create a directory corresponding to the shared directory in the edit output table file<br />
![](./media/nfs/nfs_8.jpg)

6. Open "Computer Management", click Services, find NFS Server, right-click and select Restart<br />
(If it is stopped after restarting, it can be restored by restarting the computer)<br />
![](./media/nfs/nfs_2.jpg)

7. After the restart is complete, open the nfs server and click Output. If this configuration appears, it means that the nfs service has been started<br />
![](./media/nfs/nfs_4.jpg)

8. Connect the device to the computer through a network cable, open the network configuration, click Change Adapter, find the Ethernet corresponding to the device, right-click Properties, and modify IPv4<br />
![](./media/nfs/nfs_5.jpg)

9. Windows and the device ping each other. If the ping can succeed, the network configuration is successful. (If ping from the device fails, you can turn off the firewall)<br />
![](./media/nfs/nfs_6.jpg)

10. Enter the command to mount nfs<br />
![](./media/nfs/nfs_7.jpg)

11. You can create a file in the mounting directory to verify whether the mounting is successful.
