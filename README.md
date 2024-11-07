##Creating a VPN server on Linux
### To create a VPN server on Linux with OpenVPN OVF sample file you should go through these steps:
Download an OVF sample file for a virtual machine. It's initially designed for ESXi hypervisor which only runs on a bare metal, but in my case Oracle VirtualBox version 7.0.18
perfectly runs my new virtual machine based on this file.

![download OVF](https://github.com/user-attachments/assets/b8d0acca-37bf-4ab8-8fa1-c2eac56d4207)

Open your downloaded file in your virtual hypervisor. It is already set, no additional changes in configuration required.


<p align="center">
<img src="https://github.com/user-attachments/assets/32aeb6fd-fbfa-4b54-a15a-8f737250c675">
</p>

Start imported virtual machine. Wait till preinstallation is complete. Follow the guidance on the OpenVPN official site, enter login and password (also on the site). Read and accept the agreement.

<p align="center">
<img src="https://github.com/user-attachments/assets/800271ec-17fd-4f06-a139-9fc9d3dc3730">
<img src="https://github.com/user-attachments/assets/8fce734c-53ff-4f61-a5c5-ddd68df2cc7a">
</p>

Go through basic setup wizard.

<p align="center">
<img src="https://github.com/user-attachments/assets/0e2ae27b-80e7-4da8-a3d7-9913a45c4fc1">
<img src="https://github.com/user-attachments/assets/45e10b2a-9d4b-4b84-884f-37a41cadd8dc">
</p>

Go to the provided link and login with your username and password. Accept the agreement. Add a new client profile.

<p align="center">
<img src="https://github.com/user-attachments/assets/b6f8ba5c-465e-40f6-b84b-91931286517b">
<img src="https://github.com/user-attachments/assets/287a4cb4-b3f3-4fd0-9edb-0c58680a1bd1">
</p>

Once profile is created a file like this will be automatically downloaded to your pc.

<p align="center">
<img src="https://github.com/user-attachments/assets/8bc5bc62-cf1e-4894-858c-efec4332e4c0">
</p>

To make a connection with your VPN access server you need to install openvpn3. I used the following guidance.

<p align="center">
<img src="https://github.com/user-attachments/assets/ff7dbf40-9122-4396-ab98-8f8cedf1667a">
</p>

during installation of openvpn3 similar files will be created

<p align="center">
<img src="https://github.com/user-attachments/assets/44bdec92-72c0-42aa-bb2a-b2b90384c75b">
</p>

Once openvpn3 is downloaded use downloaded file and CLI to make a connection with this command: <br>
`openvpn3 session-start --config *your profile file*`

<p align="center">
<img src="https://github.com/user-attachments/assets/e6f53256-77ef-4ea9-8a0c-2c1976e96c54">
</p>

If everything is done right a connection should be successfully established.
<br>
<br>
<br>
<br>
Unfortunately I cannot assign myself a static ip address so there is basically no way I can connect my VPN access server remotly. It's better to launch an access server on a remote hosted machine, it's already has it's address and could be connected remotly.

<p align="center">
<img src="https://github.com/user-attachments/assets/a968c99c-9d74-4ab4-9ae9-4dac874c2d19">
</p>

