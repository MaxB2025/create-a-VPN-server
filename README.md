# Create a VPN server on Linux
### To create a VPN server on Linux with OpenVPN OVF sample file you should go through these steps:
Download an OVF sample file for a virtual machine. It's initially designed for ESXi hypervisor which only runs on a bare metal, but in my case Oracle VirtualBox version 7.0.18
perfectly runs my new virtual machine based on this file.

<p align="center">
<img src="https://github.com/user-attachments/assets/4fa39a2a-425f-41dc-bc81-18e1564fdfbc">
</p>

Open your downloaded file in your virtual hypervisor. It is already set, no additional changes in configuration required.

<p align="center">
<img src="https://github.com/user-attachments/assets/435b0197-595c-4fb0-83f0-7e895db3fb37">
</p>

Start imported virtual machine. Wait till preinstallation is complete. Follow the guidance on the OpenVPN official site, enter login and password (also on the site). Read and accept the agreement.

<p align="center">
<img src="https://github.com/user-attachments/assets/f7a3d1e2-74c7-427f-b643-eb08f7e10655">
<img src="https://github.com/user-attachments/assets/fb1b6b46-e534-4792-b3bb-6a01136a9cb4">
</p>

Go through basic setup wizard.

<p align="center">
<img src="https://github.com/user-attachments/assets/1402242a-5b4a-4e84-b853-ae3e925643f2">
<img src="https://github.com/user-attachments/assets/cfeca06e-65f9-4a64-9c16-b6d61ba4bc3e">
</p>

Go to the provided link on a machine that you want to be connected to VPN. Login with your username and password. Accept the agreement. Add a new client profile.

<p align="center">
<img src="https://github.com/user-attachments/assets/82b38b13-a955-453c-b1ea-f51566a09240">
<img src="https://github.com/user-attachments/assets/edcb6822-1820-4b5a-aa23-92e8f408f8dc">
<img src="https://github.com/user-attachments/assets/cee75904-fae8-4dfd-bdd8-5d98d87f7979">
<img src="https://github.com/user-attachments/assets/7b6637fe-7a9d-4b8b-b4e7-df39e59b1a89">
</p>

Once profile is created a file like this will be automatically downloaded to your pc.

<p align="center">
<img src="https://github.com/user-attachments/assets/e53a88b3-d47a-4cbf-956e-e029ea65b098">
</p>

To make a connection with your VPN access server you need to install openvpn3. I used the following guidance.

<p align="center">
<img src="https://github.com/user-attachments/assets/0f0e50f7-f66e-4868-aa6a-5327889c7162">
</p>

during installation of openvpn3 similar files will be created

<p align="center">
<img src="https://github.com/user-attachments/assets/bf35d9b3-507b-4d2b-b4fc-d92265d60b3e">
</p>

Once openvpn3 is downloaded use downloaded file and CLI to make a connection with this command: <br>
`openvpn3 session-start --config *your profile file*`

<p align="center">
<img src="https://github.com/user-attachments/assets/d7509c81-9787-4052-816d-4858bb231f13">
</p>

If everything is done right a connection should be successfully established.
<br>
<br>
<br>
<br>
Unfortunately I cannot assign myself a static ip address so there is basically no way I can connect my VPN access server remotly. It's better to launch an access server on a remote hosted machine, it's already has it's address and could be connected remotly.

<p align="center">
<img src="https://github.com/user-attachments/assets/39900ad6-ba8a-4ec4-86f0-d494e21a97f8">
</p>

## References:
[OpenVPN for home labs](https://theithollow.com/2014/02/10/open-vpn-home-labs/)<br>
[OpenVPN solutions](https://openvpn.net/)<br>
[VMWare ESXi Virtual Appliance Quick Start Guide](https://openvpn.net/as-docs/esxi.html#invalid-certificate-44977)<br>
[openvpn3 download manual](https://openvpn.net/cloud-docs/tutorials/configuration-tutorials/connectors/operating-systems/linux/tutorial--learn-to-install-and-control-the-openvpn-3-client.html)
