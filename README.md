# Network-Security-Lab-Using-Pfsense
## What is Network Security?

Network security encompasses all the steps taken to protect the integrity of a computer network and the data within it. Network security is important because it keeps sensitive data safe from cyber attacks and ensures the network is usable and trustworthy. Successful network security strategies employ multiple security solutions to protect users and organizations from malware and cyber attacks, like distributed denial of service.

## Why is Network Security Important?

Network security is critical because it prevents cybercriminals from gaining access to valuable data and sensitive information. When hackers get hold of such data, they can cause a variety of problems, including identity theft, stolen assets and reputational harm.

The following are four of the most important reasons why protecting networks and the data they hold is important:

1. **Operational risks.** An organization without adequate network security risks disruption of its operations. Businesses and personal networks depend on devices and software that cannot operate effectively when compromised by viruses, malware and cyber attacks. Business also rely on networks for most internal and external communication.
2. **Financial risks for compromised personally identifiable information (PII).** Data breaches can be expensive for both individuals and businesses. Organizations that handle [PII](https://www.techtarget.com/searchsecurity/definition/personally-identifiable-information-PII), such as Social Security numbers and passwords, are required to keep it safe. Exposure can cost the victims money in fines, restitution and repairing compromised devices. 
3. **Financial risk for compromised intellectual property.** Organizations can also have their own [intellectual property](https://www.techtarget.com/whatis/definition/intellectual-property-IP) stolen, which is costly. The loss of a company's ideas, inventions and products can lead to loss of business and competitive advantages.
4. **Regulatory issues.** Many governments require businesses to comply with data security regulations that cover aspects of network security. For example, medical organizations in the United States are required to comply with the regulations of the Health Insurance Portability and Accountability Act ([HIPAA](https://www.techtarget.com/searchhealthit/definition/HIPAA)).

## Project Introduction

This project is about designing and implementing a **network security lab environment using pfSense** as the firewall/router, with **two isolated LANs** to simulate a real-world network. pfSense is an open-source firewall that provides routing, NAT, VPN, IDS/IPS, and traffic filtering capabilities. By setting up multiple LANs, you can test **segmentation, access control, intrusion prevention, and monitoring**, which are critical in enterprise cybersecurity.

This lab mirrors a real corporate setup where multiple departments or zones (e.g., **Office LAN** and **Server LAN**) are kept separate for security but still managed through one firewall.

![Pfsense_pages-to-jpg-0001](https://github.com/user-attachments/assets/b0859f34-2748-4827-946e-f5001e03846f)

### Lab Setup

- **Firewall** : pfSense
- **WAN**: Connected to host (simulating internet access)
- **LAN1** : Employee network
- **LAN2** : Server network
- **VMs**: Windows/Linux systems inside each LAN for testing

## Step by Step Process

1. Creating Different Network for the Employee and Server Network. So Open “ **Virtual Network Editor As Administrator “.**

<img width="500" height="500" alt="Screenshot 2025-08-15 230606" src="https://github.com/user-attachments/assets/3becdd78-4817-4ebd-81dd-3d2c4fcb921b" />


1. Now keep the **NAT Network** as it is, if you want you can change the IP to a simple one like the below image.
2. Then Create **Two Networks for LAN 1 and LAN 2** by clicking on the Add Network Button and Make sure to create them as **Host Only Type Network**.
3. Then Click on **Apply** to apply the changes. 

<img width="500" height="500" alt="Screenshot 2025-08-15 231052" src="https://github.com/user-attachments/assets/f2e41927-a2db-40a3-9776-cd672ae4269b" />


1. Now open **VMware** and Create a **New VM** for the **Pfsense.**

<img width="500" height="500" alt="Screenshot 2025-08-16 111904" src="https://github.com/user-attachments/assets/0ebdb67c-38b9-4969-aff6-9b51ab268432" />


1. Now select the ISO image of Pfsense and click on **Next.**

<img width="500" height="500" alt="Screenshot 2025-08-16 111824" src="https://github.com/user-attachments/assets/98ff9eaa-4315-46b4-8891-8c68307b9d77" />


1. **Name the VM** as you please and choose the **Location** for saving the file of the VM.

<img width="500" height="500" alt="Screenshot 2025-08-16 112005" src="https://github.com/user-attachments/assets/227002b4-808e-407a-be4e-650caca3547b" />


1. **Allocate disk size** for the VM and click on **Next.**

<img width="500" height="500" alt="Screenshot 2025-08-16 112118" src="https://github.com/user-attachments/assets/206a8068-ed30-43ba-a866-991edb0715dd" />


1. Now click on **Customize Hardware** and Set the network adapter to “ **Custom : VMnet8 (NAT) “** and Click on **Advanced** and Generate **MAC Address for the Network Adapter of NAT.** Then click on ok to confirm.

<img width="500" height="500" alt="Screenshot 2025-08-16 112149" src="https://github.com/user-attachments/assets/9cf542a0-5cde-47ad-8e76-6e1ec67f1ac5" />


<img width="600" height="500" alt="Screenshot 2025-08-16 112248" src="https://github.com/user-attachments/assets/146c34b0-eb64-4b38-8429-1c0dfe0a72d1" />


<img width="500" height="500" alt="Screenshot 2025-08-16 112318" src="https://github.com/user-attachments/assets/f9451519-1bdc-4365-84fa-c32ae220c622" />


1. Now Click on **Add option** and select **Network Adapter to Add Another Two Network Adapter**. Now repeat the same process as before but the Network Type of the another two adapters are “ **Custom : VMnet1 (Host-only) & Custom : VMnet2 (Host-only) “** and Then Generate **MAC Address for the Both Adapters.**

<img width="500" height="500" alt="Screenshot 2025-08-16 112715" src="https://github.com/user-attachments/assets/0ed2a1b5-01df-49d0-968d-db56cc0637c8" />


<img width="600" height="500" alt="Screenshot 2025-08-16 113427" src="https://github.com/user-attachments/assets/bbb0ebac-91c7-4db5-a589-0e10f0cbd47f" />


<img width="500" height="500" alt="Screenshot 2025-08-16 113519" src="https://github.com/user-attachments/assets/d84ef852-b0dc-4bbe-8cf6-fc5245d9a1d7" />


1. Now click on **Close and Finish** the process and **Power On** the VM.

<img width="500" height="500" alt="Screenshot 2025-08-16 113620" src="https://github.com/user-attachments/assets/21dc2c71-d972-4da9-bce1-14a1c6a14eef" />

<img width="600" height="500" alt="Screenshot 2025-08-15 225712" src="https://github.com/user-attachments/assets/c5c6de21-b02e-4d05-a7ab-1f1633066d1a" />

1. Now , wait until the Booting process is over.

<img width="500" height="500" alt="Screenshot 2025-08-15 225858" src="https://github.com/user-attachments/assets/86e51b96-df9a-41ab-9d72-0422871e7fe3" />

1. Now click on **Accept** in the copyrights page and in the Next two Page Click On **Enter** button in your Keyboard to select **OK** option**.**

<img width="748" height="425" alt="Screenshot 2025-08-15 225953" src="https://github.com/user-attachments/assets/80a11a91-314b-4725-8720-fd1c9a871152" />


<img width="737" height="418" alt="Screenshot 2025-08-15 230029" src="https://github.com/user-attachments/assets/caadeb3e-3692-47e0-8c35-b098f684bee3" />


<img width="720" height="397" alt="Screenshot 2025-08-16 113914" src="https://github.com/user-attachments/assets/7709219a-fad4-4785-9571-284ba497a53b" />



1. Now Select the Adapter interface for **WAN** and click on **OK.**

<img width="719" height="402" alt="Screenshot 2025-08-16 114010" src="https://github.com/user-attachments/assets/de89f8e6-6821-49ba-bdab-4b6ad3a26dd3" />

<img width="719" height="399" alt="Screenshot 2025-08-16 114422" src="https://github.com/user-attachments/assets/31f14ff3-0b33-41d4-b2f6-9378717c8909" />

<img width="711" height="401" alt="Screenshot 2025-08-16 130614" src="https://github.com/user-attachments/assets/b73bccaa-1c3b-4374-a09d-0a3b375b3fd0" />

<img width="720" height="405" alt="Screenshot 2025-08-16 133856" src="https://github.com/user-attachments/assets/a8c95822-c8ce-47e4-ba94-655b23e84a3c" />

<img width="720" height="411" alt="Screenshot 2025-08-16 131147" src="https://github.com/user-attachments/assets/02ee01c1-b5cd-45ee-bf64-a45f03fea79a" />

<img width="723" height="382" alt="Screenshot 2025-08-16 133009" src="https://github.com/user-attachments/assets/61599809-3033-4a34-996c-ee6b081e340e" />

<img width="722" height="395" alt="Screenshot 2025-08-16 141708" src="https://github.com/user-attachments/assets/9eedbf3c-ebe4-4981-8e35-c4b1359f8410" />

<img width="724" height="408" alt="Screenshot 2025-08-16 141921" src="https://github.com/user-attachments/assets/fcd9ff62-fd85-4491-87c4-ecbcdfc9374e" />

<img width="708" height="405" alt="Screenshot 2025-08-16 142013" src="https://github.com/user-attachments/assets/20aa177e-0131-4c64-a35a-aa6eddff9872" />

<img width="720" height="405" alt="Screenshot 2025-08-16 142052" src="https://github.com/user-attachments/assets/5e504d89-ca0f-4534-8a66-fd6af50c59d5" />

<img width="715" height="400" alt="Screenshot 2025-08-16 142144" src="https://github.com/user-attachments/assets/e9bf715c-2e34-4e84-9e97-b5577c75689b" />

<img width="707" height="344" alt="Screenshot 2025-08-16 142216" src="https://github.com/user-attachments/assets/ddf739c1-f186-4e03-a272-a06f1a4835ae" />

<img width="718" height="378" alt="Screenshot 2025-08-16 142245" src="https://github.com/user-attachments/assets/2e9b98c5-d837-4dc4-a9bc-d1590efba928" />

<img width="707" height="395" alt="Screenshot 2025-08-16 142330" src="https://github.com/user-attachments/assets/488a385b-a1b4-4be8-ac09-cc335cec488f" />

<img width="705" height="384" alt="Screenshot 2025-08-16 143318" src="https://github.com/user-attachments/assets/4d0d45e4-f3cf-44ae-a4e5-c364dabf2b24" />

<img width="718" height="297" alt="Screenshot 2025-08-16 143401" src="https://github.com/user-attachments/assets/2afebb41-8f56-41d2-8ca3-e9949af7df79" />

<img width="642" height="415" alt="Screenshot 2025-08-16 143643" src="https://github.com/user-attachments/assets/2727d4e6-57df-48d0-850d-48d4b70c885c" />

<img width="707" height="398" alt="Screenshot 2025-08-16 144546" src="https://github.com/user-attachments/assets/280e869f-4002-4f8d-a382-09b1ad379ace" />

<img width="646" height="415" alt="Screenshot 2025-08-16 144743" src="https://github.com/user-attachments/assets/dd73fb3c-64d1-4339-9e62-c9ee3fe29010" />

<img width="662" height="416" alt="Screenshot 2025-08-16 145036" src="https://github.com/user-attachments/assets/207dc8ef-6675-48ee-8eb1-39a14895acf4" />

<img width="724" height="415" alt="Screenshot 2025-08-16 145309" src="https://github.com/user-attachments/assets/4206926f-3dc2-4a77-81bf-dc4dd5689a23" />

<img width="567" height="418" alt="Screenshot 2025-08-16 152105" src="https://github.com/user-attachments/assets/6af38a83-41b1-4fb3-a26b-b85a9d17a4c1" />

<img width="726" height="419" alt="Screenshot 2025-08-17 133140" src="https://github.com/user-attachments/assets/7602f0e0-20b9-4ff9-aca6-97b744d18a90" />

<img width="1862" height="849" alt="Screenshot 2025-08-18 223633" src="https://github.com/user-attachments/assets/1f6f3d38-29a7-4fc9-a013-e0df206f67bf" />

<img width="1866" height="918" alt="Screenshot 2025-08-18 223553" src="https://github.com/user-attachments/assets/b7986a58-7629-45b9-92bf-cd99c89aefaf" />

<img width="1810" height="944" alt="Screenshot 2025-08-18 223800" src="https://github.com/user-attachments/assets/d39e6476-43df-48b3-9a8f-c1af404033c2" />

<img width="1914" height="1001" alt="image" src="https://github.com/user-attachments/assets/a1791748-91d4-4d5d-a407-8e2688534f0a" />

<img width="1904" height="839" alt="image" src="https://github.com/user-attachments/assets/ffeacb17-0ab1-43c1-9c37-abf563ce235b" />

<img width="1919" height="995" alt="image" src="https://github.com/user-attachments/assets/66d7963a-fb2b-4914-a2a4-4c092ec5ce7d" />

<img width="1919" height="839" alt="image" src="https://github.com/user-attachments/assets/86e48a09-f953-4f91-bca1-56c252ac156c" />









