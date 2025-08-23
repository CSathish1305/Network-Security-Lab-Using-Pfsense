# Network-Security-Lab-Using-Pfsense
## What is network security?

Network security encompasses all the steps taken to protect the integrity of a computer network and the data within it. Network security is important because it keeps sensitive data safe from cyber attacks and ensures the network is usable and trustworthy. Successful network security strategies employ multiple security solutions to protect users and organizations from malware and cyber attacks, like distributed denial of service.

## Why is network security important?

Network security is critical because it prevents cybercriminals from gaining access to valuable data and sensitive information. When hackers get hold of such data, they can cause a variety of problems, including identity theft, stolen assets and reputational harm.

The following are four of the most important reasons why protecting networks and the data they hold is important:

1. **Operational risks.** An organization without adequate network security risks disruption of its operations. Businesses and personal networks depend on devices and software that cannot operate effectively when compromised by viruses, malware and cyber attacks. Business also rely on networks for most internal and external communication.
2. **Financial risks for compromised personally identifiable information (PII).** Data breaches can be expensive for both individuals and businesses. Organizations that handle [PII](https://www.techtarget.com/searchsecurity/definition/personally-identifiable-information-PII), such as Social Security numbers and passwords, are required to keep it safe. Exposure can cost the victims money in fines, restitution and repairing compromised devices. 
3. **Financial risk for compromised intellectual property.** Organizations can also have their own [intellectual property](https://www.techtarget.com/whatis/definition/intellectual-property-IP) stolen, which is costly. The loss of a company's ideas, inventions and products can lead to loss of business and competitive advantages.
4. **Regulatory issues.** Many governments require businesses to comply with data security regulations that cover aspects of network security. For example, medical organizations in the United States are required to comply with the regulations of the Health Insurance Portability and Accountability Act ([HIPAA](https://www.techtarget.com/searchhealthit/definition/HIPAA)).

## Project Introduction

This project is about designing and implementing a **network security lab environment using pfSense** as the firewall/router, with **two isolated LANs** to simulate a real-world network. pfSense is an open-source firewall that provides routing, NAT, VPN, IDS/IPS, and traffic filtering capabilities. By setting up multiple LANs, you can test **segmentation, access control, intrusion prevention, and monitoring**, which are critical in enterprise cybersecurity.

This lab mirrors a real corporate setup where multiple departments or zones (e.g., **Office LAN** and **Server LAN**) are kept separate for security but still managed through one firewall.

![Pfsense_removed_page-0001.jpg](attachment:ae8132f3-f055-4b7f-81f8-f1058bff8a98:1103c8ca-5eee-4ef8-bb86-f13c5128d5ac.png)

### Lab Setup

- **Firewall** : pfSense
- **WAN**: Connected to host (simulating internet access)
- **LAN1** : Employee network
- **LAN2** : Server network
- **VMs**: Windows/Linux systems inside each LAN for testing

## Step by Step Process

1. Creating Different Network for the Employee and Server Network. So Open “ **Virtual Network Editor As Administrator “.**

![Screenshot 2025-08-15 230606.png](attachment:5ad1b21e-9531-49b8-b6b3-d122ce27e4b7:Screenshot_2025-08-15_230606.png)

1. Now keep the **NAT Network** as it is, if you want you can change the IP to a simple one like the below image.
2. Then Create **Two Networks for LAN 1 and LAN 2** by clicking on the Add Network Button and Make sure to create them as **Host Only Type Network**.
3. Then Click on **Apply** to apply the changes. 

![image.png](attachment:77bb35ff-ad9e-4838-8f8b-800decb533af:image.png)

1. Now open **VMware** and Create a **New VM** for the **Pfsense.**

![image.png](attachment:587efa10-2c37-4ead-a7ea-351b757e2cba:image.png)

1. Now select the ISO image of Pfsense and click on **Next.**

![image.png](attachment:87879b34-ac38-4365-9ef3-7865883f10be:image.png)

1. **Name the VM** as you please and choose the **Location** for saving the file of the VM.

![image.png](attachment:7a6f4ff0-b89c-497e-83a6-1426bdcf8d18:image.png)

1. **Allocate disk size** for the VM and click on **Next.**

![image.png](attachment:246c714f-2d42-4329-95f9-1fefae5283f4:image.png)

1. Now click on **Customize Hardware** and Set the network adapter to “ **Custom : VMnet8 (NAT) “** and Click on **Advanced** and Generate **MAC Address for the Network Adapter of NAT.** Then click on ok to confirm.

![image.png](attachment:7d24126a-880f-4b26-8fad-90fb8afa364e:image.png)

![image.png](attachment:9cec0528-c173-4c42-8b8a-b8e01a9a8389:image.png)

![image.png](attachment:aeae6f16-2766-4a50-ba2f-3528024b1d16:image.png)

1. Now Click on **Add option** and select **Network Adapter to Add Another Two Network Adapter**. Now repeat the same process as before but the Network Type of the another two adapters are “ **Custom : VMnet1 (Host-only) & Custom : VMnet2 (Host-only) “** and Then Generate **MAC Address for the Both Adapters.**

![image.png](attachment:3c445445-8bb4-4ab9-908f-dadfb901a9bd:image.png)

![image.png](attachment:ee5d9490-52b6-4b0a-893d-fee169b2520e:image.png)

![image.png](attachment:66906b0a-3bd0-4b61-b32b-9ae8b2d1454b:image.png)

1. Now click on **Close and Finish** the process and **Power On** the VM.

![image.png](attachment:94e66f7a-60c8-47a3-b287-8ec7c68286cf:image.png)

![image.png](attachment:62688371-e356-4c91-bf2a-a1028ad9aa4f:image.png)

1. Now , wait until the Booting process is over.

![image.png](attachment:37c0cc10-f26d-4605-a19c-0a676c5228e8:image.png)

1. Now click on **Accept** in the copyrights page and in the Next two Page Click On **Enter** button in your Keyboard to select **OK** option**.**

![image.png](attachment:4b26d186-dbf9-4dd2-9922-001830a4cde7:image.png)

![image.png](attachment:340a00c4-d030-49bb-b46e-6a7177b25955:image.png)

![image.png](attachment:189aaa9d-1124-4d49-8f99-e63f7aaed220:image.png)

1. Now Select the Adapter interface for **WAN** and click on **OK.**

![image.png](attachment:cd8e127a-67c5-4703-9d21-98a218f47ba1:image.png)

1. 

![image.png](attachment:78a66cd7-98bc-47a9-96f2-a4d3ee1a6513:image.png)

![image.png](attachment:51e5829d-c4a4-4a2a-87af-2235526aaf9d:image.png)

![image.png](attachment:ca6cc72d-db70-43ac-941c-1eaa6dedaf53:image.png)

![image.png](attachment:719a1fae-f522-4ef8-9e89-7cb0f30c9078:image.png)

![image.png](attachment:9986b2af-696b-498b-80ff-dc47ed2d16c8:image.png)

![image.png](attachment:79abca88-cb4c-47d0-b90a-1ebae536668c:image.png)

![image.png](attachment:cae5f77b-a1f9-43fc-ab3f-35394a302cfe:image.png)

![image.png](attachment:91ccd8e8-aa2a-46e4-b986-b92320963790:image.png)

![image.png](attachment:c66cfa2f-6582-4a60-a911-c802a855fd22:image.png)

![image.png](attachment:198841b1-53d5-4080-a889-be66f9153ca5:image.png)

![image.png](attachment:d8d3d52c-b27d-4d49-b36b-7c301194df5d:image.png)

![image.png](attachment:85fc90b2-55ab-46ed-ab73-5afb6be0a5bf:image.png)

![image.png](attachment:0c8a5443-b935-4415-8eff-ae44dfa27c3a:image.png)

![image.png](attachment:36caaf47-fa1c-41e8-8ebd-e8bc8f492158:image.png)

![image.png](attachment:977bdc21-0671-4373-91c1-d1bb862fdc61:image.png)

![image.png](attachment:943a2120-0688-4cbf-a363-025917f1fe24:image.png)

![image.png](attachment:b94c391e-b3ff-45a9-92d5-8a9543b27c17:image.png)

![image.png](attachment:a67213af-17fe-45d8-8cba-8ab54ea0bd99:image.png)

![image.png](attachment:29a688e7-a0f1-4603-9a16-683d48029229:image.png)

![image.png](attachment:bfd1e6bc-45f0-4d7e-81d3-3f01d54e1cbf:image.png)

![image.png](attachment:0238fac1-2158-42ba-80e2-0825c8d4ce38:image.png)

![image.png](attachment:8ee5aae9-0557-45ca-94e1-eda9cbfc5b5e:image.png)

![image.png](attachment:d0cdaa22-31a5-4a2f-990b-26cca0406f11:image.png)

![image.png](attachment:22b01fa3-9287-480b-a744-19f1c7af40cb:image.png)

![image.png](attachment:1d825463-d978-4fe7-9ed2-15cad9561daa:image.png)

![image.png](attachment:bca26f3e-3aa3-472a-9edb-b540dd96ee39:image.png)

![image.png](attachment:4a62a957-7793-4d09-a930-3d98667a73b4:image.png)

![image.png](attachment:add0c998-b579-4eb2-9d07-30f6aad2ae1f:image.png)
