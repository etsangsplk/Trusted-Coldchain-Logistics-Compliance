# Trusted-Coldchain-Logistics-Compliance
Chaincode for Trusted Coldchain Logistics Compliance (Use Case) which has been developed as part of IBM Inside Track 2017 program.It uses Hyper ledge Fabric 0.6v and Blockchain Service from IBM BlueMix Cloud Platform. 

Update: 05/29
Added BNA (Business Network Archive) equivalent file for simulation the same blockchain transaction in Hyperledger Composer Playground. 

# Business Problem 
The problem we have tried to address here cold chain logistics which needs to be kept under controlled temperature, say between -50 Celsius to 50 Celsius. Such medical shipments could be in the form of temperature controlled medicines (drugs, injections etc), human tissues (such as umbilical cord stem cells), clinical trial substance and even research chemicals. When due to technical, logistical or environments reasons, temperature cannot be controlled/maintained, the cold chain gets broken and the medical shipment gets damaged i.e. it is unusable. Today shippers usually insure their packages for covering the losses caused during the shipping process. There could be separate trained medical practitioners at the point of origin and at the destination to manually verify the shipments whether they are spoiled or intact. If found spoilt the consignee would manually fill out an insurance claim form, logistics provider acknowledgement and submit it to the Insurance company which takes a significant time to verify all the details mentioned are correct before releasing the compensation to the claimer. This is a time consuming and very in-efficient process for everyone included in the transaction. On the other hand, because the consignee has now received a damaged shipment, the consignee now needs to arrange for alternatives which could cause further delays to patient care or clinical trials.

# Solution 
Our solution addresses this problem through the use of IOT and Block chain technologies. As part of this solution, an independent third party will act as the trusted advisory between the shipper, logistics provider, consignee and insurance provider through the use of Blockchain and IOT. The shipment (individual or group) will be tagged with a tamper proof IOT sensor capable of measuring temperature and humidity. This telemetry information will be sent to a centrally managed application which would then validate if the temperate is within the threshold limits. Incase the temperature crosses that threshold then a transaction will be registered within the block chain network for that shipment. Such a block chain transaction will be the sole trusted representation that the package has been damaged. This information can now be used near real time by insurance provider to initiate claim settlements as well as by the consignee to initiate new demands for the same shipment thereby reducing time, effort, cost which is associated in today’s world.

The proposed system will be able to address the issue of time delay in processing individual insurance claims the management is submitted with. The proposed system will also act as a trusted third party for all actors/parties involved with respect to shipments compliance with cold chain temperature.
Our Proposal is a trusted system that introduces an IOT enabled digital temperature sensor devices that can track the temperature of the shipments with regular intervals i.e. every 10 seconds. This reading is communicated to an independently hosted IOT foundation server. If this IOT foundation server detects an anomaly in the temperature beyond the specific threshold it sends out a signal to the blockchain network to record such a transaction.

# Smart Contract Functionality (Chaincode) 
1. create () --> Create new package with status ‘Label_Generated’ and store the details in blockchain (irrespective of Shipper)
2. acceptpkg() --> Transfer the package ownership from Shipper to Logistic Provider. Change the status of package to ‘In_Transit’ and store  it in blockchain.  Also validate Logistic Provider whether the package is designated to him or not.
3. updatetemp() --> Update the status of package based on the current supplied temperature (irrespective of parties)
4. deliverpkg() --> Update status of package to ‘Pkg_Delivered’ at the time of delivery of package to assignee. 
5. queryallpkg() --> Query all package present in blochchain (irrespective of Package Staus)
6. querybyroleandstatus() --> Query blockchain by party role, role-value and package status. 

# Migration to Hyper Ledger Framework 1.0
Business Network Archive file equivalent to Hyper Ledger Fabric Composer 1.0. This file can be uploaded directly to <B>Hyperledger Composer Playground <B> https://composer-playground.mybluemix.net/editor and blockchain transaction can be simulated.
