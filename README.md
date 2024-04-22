## MULTI CHANNEL ARCHITECTURE WITH CONTAINERIZED MQ: 

**GITHUB**:* [https://github.com/maktup/MULTI-CHANNEL-ARCHITECTURE-WITH-CONTAINERIZED-MQ.git](https://github.com/maktup/MULTI-CHANNEL-ARCHITECTURE-WITH-CONTAINERIZED-MQ.git)*

## 1. CONTEXT:
The following article shows how to configure a **MULTI-CHANNEL** architecture in a **CONTAINERIZED MQ** environment on **OPENSHIFT**.

*"CURRENTLY A GREAT UNCERTAINTY OF CUSTOMERS IS TO KNOW HOW THEY CAN REPLICATE A SET OF MQM THAT THEY HAD IN OMPREMISE, BUT NOW ABOUT OPENSHIFT"*

This **ARTICLE** covers all of this in relation to handling and configuration, the **TOPICs** are as follows:

## 2. ARCHITECTURE:
The following **ARCHITECTURE** shows how the different **RESOURCES** used within the **OPENSHIFT** cluster and the interaction with the **MQMs**.

![alt text](https://github.com/maktup/MULTI-CHANNEL-ARCHITECTURE-WITH-CONTAINERIZED-MQ/blob/main/IMAGE/Architecture.jpg?raw=true)

## 3. INSTALLATION (MQv9 INSTANCE):
Here we proceed to show the installation of** Containerized MQ** based on Yaml **SCRIPTs** on **OPENSHIFT**.

To design the solution, it is required to create** 3 INSTANCES** of MQMs, based on the shared **SCRIPT**: 

- **NOMBRE INSTANCIA: **ins-mq-001
- **NOMBRE MQ MANAGER:** MQM.1

- **NOMBRE INSTANCIA: **ins-mq-002
- **NOMBRE MQ MANAGER: **MQM.2

- **NOMBRE INSTANCIA: **ins-mq-003
- **NOMBRE MQ MANAGER:** MQM.3- 

These **SCRIPT MQM** instances will be created of type **EPHEMERAL**, but in a real environment they should be considered creating type: **PERSISTENT** (associated with a **STORAGE**).

## 4. CONFIGURATION OF: 'MQv9 ARCHITECTURE IN CP4I':
Here we proceed to show the **ARCHITECTURE** of the proposed solution:

![alt text](https://github.com/maktup/MULTI-CHANNEL-ARCHITECTURE-WITH-CONTAINERIZED-MQ/blob/main/IMAGE/Architecture.jpg?raw=true)

The **COMPONENTS** that are worked on in the creation are:

-  MQM.1. 
-  LOCAL-QUEUE (TRANSMISIÓN).
-  REMOTE-QUEUE. 
-  ALIAS-QUEUE.
-  CANAL DE APLICACIÓN.
-  CANAL MQ-MANAGER (EMISOR).
-  CANAL MQ-MANAGER (RECEPTOR).

## 5. CONNECTION OF: 'MQ-MANAGERs' (CHANNELS):
Here the **CONFIGURATION** for communication between the **MQMs** is shown, through the **SENDER CHANNELS** & **RECEIVER CHANNELS**, in each of them.

After the **CONFIGURATION** for communication between the **MQMs**, through the **SENDER CHANNELS** & **RECEIVER CHANNELS**, in each of them
  
## 6.TESTING: 'SENDING MESSAGE':
Here the tests carried out in relation to how **MESSAGES** flow around the **ARCHITECTURE** are shown.
   
To test the design of the **ARCHITECTURE** worked on, a **CLIENT** developed in **JAVA** will be used, which will connect to **MQM.1** & through the **APPLICATION CHANNEL** to send a **MESSAGE** to **AQ.1**, which will internally replicate the **MESSAGE** to **RQ1** and it is sent to** LQ.1 (transfer)**, so that it sends the **MESSAGE** through the **MQ-MANAGER CHANNELS** to **LQ1** within **MQM.2**.

**REFERENCE LINKS:**
For more complete detail, you can review the shared **STEP**-by-**STEP PDF**: '**Multichannel MQ Architecture Configuration (Openshift)'**.

![alt text](https://github.com/maktup/MULTI-CHANNEL-ARCHITECTURE-WITH-CONTAINERIZED-MQ/blob/main/IMAGE/TestingFromJava.jpg?raw=true)

