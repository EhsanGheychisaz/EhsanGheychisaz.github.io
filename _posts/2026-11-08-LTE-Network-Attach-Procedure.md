---
layout: post
title: "LTE Network Attach Procedure"
date: 2026-11-08
---


This document explains how a mobile device connects to a 4G LTE network. This process is called the **LTE Attach Procedure**.

The main purpose of this procedure is to allow a mobile device to connect to the mobile network, receive an IP address, and access external networks such as the Internet.

During this process, different network elements communicate with each other using specific protocols and messages. Each element has a particular responsibility, such as user authentication, IP address allocation, and data transmission.

This topic is important for Computer Science and Computer Engineering students because it helps them understand how mobile networks work, how network elements communicate, and how protocols are used in real-world communication systems.

The following explanation focuses on the interactions between network elements rather than the detailed technical implementation.

> **Note:** In this explanation, the terms *UE* and *user* are sometimes used interchangeably to make the text easier to read. However, they have different meanings in technical standards. Also, the word *subscriber* refers to the mobile network customer and their SIM card information.

---

## Step 1 – Radio Connection Request

First, the user's device sends an **RRC (Radio Resource Control)** message to the base station, called **eNodeB**.

The purpose of this message is to establish an initial radio connection and request the radio resources needed for communication.

## Step 2 – Sending the Initial UE Message

In the second step, the eNodeB sends an **Initial UE Message** to the MME through the S1 interface, using the **S1-AP protocol**.

This message contains the initial request received from the user's device in the previous step. It also carries a NAS request message.

The MME receives this message and starts the process of connecting the user to the network.

## Step 3 – User Authentication

Now, the MME needs to communicate with the **HSS (Home Subscriber Server)** to authenticate the user.

The HSS may be located in a different city or geographical area.

The MME sends an **AIR (Authentication-Information-Request)** message to the HSS using the **Diameter protocol**.

The HSS checks the subscriber's identity and sends an **AIA (Authentication-Information-Answer)** message back to the MME.

This response contains authentication information called an **Authentication Vector (Auth Vector)**. It includes the security parameters and information needed to authenticate the user and establish encryption.

## Step 4 – Sending Authentication Information to the User

In this step, the MME sends the required authentication information to the eNodeB.

The eNodeB then forwards this information to the user's device through an RRC message.

The device receives the authentication challenge and uses the information provided to prove its identity to the network.

In simple terms, the network is checking whether the user is allowed to access the mobile network.

## Step 5 – Updating the Subscriber's Location

After the authentication process, the MME sends a **ULR (Update-Location-Request)** message to the HSS using the Diameter protocol.

This message informs the HSS that the subscriber has been authenticated and is now being served by this MME.

The HSS updates its database with the current MME information. This allows the network to find the subscriber when future services, such as calls or data connections, are needed.

After updating the information, the HSS sends a **ULA (Update-Location-Answer)** message back to the MME.

This response may contain subscriber-related information and network service parameters, such as Quality of Service (QoS) settings and bearer configuration information.

## Step 6 – Creating a Data Session

At this stage, the user's device needs an IP address to communicate with external networks, such as the Internet.

Therefore, the MME starts the session creation process by communicating with the **S-GW (Serving Gateway)** and the **P-GW (PDN Gateway)**.

This communication uses the **GTPv2-C protocol**.

The MME selects an appropriate P-GW and requests the creation of a data session.

The P-GW is responsible for assigning an IP address to the user, creating the required bearer, and applying the necessary charging and network policies.

After the session is created, the response is sent back through the gateways.

## Step 7 – Sending the Session Information to the S-GW

In this step, the P-GW sends a response containing the user's IP address and the related bearer information to the S-GW.

This information is necessary to continue setting up the user's data connection.

## Step 8 – Sending the Information to the MME

Now, the S-GW forwards the received information to the MME using the GTPv2-C protocol.

The information includes the user's IP address and the bearer identification information.

The MME uses these details to continue the connection setup process.

## Step 9 – Preparing the Radio Bearer

In this step, the MME sends the required connection information to the eNodeB through the **S1-AP protocol**.

This information includes the user's IP address, QoS parameters, and bearer identification.

The eNodeB uses these parameters to prepare the radio bearer and allocate the necessary radio resources for communication with the user's device.

## Step 10 – Sending Configuration Information to the User

The eNodeB now sends an **RRC Connection Reconfiguration** message to the user's device.

This message contains the configuration information required to complete the radio connection.

The device receives the necessary parameters and prepares itself for data communication with the mobile network.

## Step 11 – Confirming the Connection

After receiving the configuration information, the user's device applies the required settings, including the network configuration.

Then, it sends an RRC response message to the eNodeB to confirm that the configuration has been completed.

The eNodeB forwards the related confirmation to the MME through the S1-AP protocol.

This step informs the network that the radio connection setup has been successfully completed.

## Step 12 – Activating the Data Bearer

Now that the radio connection is ready, the MME sends a message to the S-GW.

The S-GW then communicates with the P-GW using the GTPv2-C protocol.

The purpose of this step is to update and activate the bearer so that the user's device can exchange data with external networks.

In other words, the network completes the remaining configuration needed for data transmission.

## Step 13 – Confirming Bearer Activation

Finally, the S-GW sends a **Modified Bearer Response** message to the MME using the GTPv2-C protocol.

This message confirms that the bearer modification process has been completed successfully.

At this point, the LTE connection setup is complete, and the user's device can communicate with external networks such as the Internet.

---

## Final Summary – What Happens During These 13 Steps?

The entire process can be divided into five main stages:

| Stage | Steps | Main purpose |
|---|---:|---|
| Radio connection | 1–2 | Establish initial communication with the base station |
| Authentication | 3–4 | Verify the user's identity |
| Subscriber registration | 5 | Update the subscriber's location information |
| IP and session creation | 6–8 | Create a data session and assign an IP address |
| Connection completion | 9–13 | Configure radio resources and activate the data bearer |

## Why Is This Important for Computer Science Students?

Understanding the LTE Attach Procedure is useful for Computer Science and Computer Engineering students for several reasons:

1. **Computer Networks:** It shows how different network elements communicate with each other.
2. **Network Protocols:** It introduces real-world protocols such as Diameter, GTPv2-C, RRC, and S1-AP.
3. **Client-Server Communication:** It helps students understand how devices communicate with network servers.
4. **IP Networking:** It explains how a mobile device receives an IP address and connects to external networks.
5. **Network Security:** It demonstrates how authentication and encryption help protect mobile communication.
6. **Distributed Systems:** It shows how multiple independent network elements work together to complete one task.

**The most important idea is that connecting a mobile phone to a 4G network is not a single action. It is a sequence of communication steps between different network elements, each responsible for a specific part of the process.**

---

## Technical Notes

The original explanation is useful as a simplified overview. However, the following points should be considered when using it in an academic report or presentation:

- In Step 4, the authentication challenge is normally carried in a NAS **Authentication Request** message forwarded through the eNodeB to the UE. It is not simply an authentication parameter sent in an RRC message.
- In Step 5, the ULA response provides subscriber profile information to the MME. The exact information depends on the subscriber's profile and network configuration.
- In Steps 6–8, session creation normally uses **Create Session Request** and **Create Session Response** messages. The response carries information such as the allocated IP address and bearer details.
- In Step 10, the RRC Connection Reconfiguration message does not itself assign the IP address to the UE. The P-GW allocates the IP address during the session creation procedure.
- In Step 13, the **Modify Bearer Response** confirms that the bearer modification procedure has completed. It does not, by itself, directly prove that the user can successfully access every external Internet service.
