# SAP S/4Hana Cloud System configuration (for your information only)

As per the scenario, we need to automatically create a **Purchase Requiistion (PR)** with the approved equipments list in the S/4HANA Cloud system.
<br/> For this we need to use the Purchase Requisition API of SAP S/4HANA Cloud system as documented in the [SAP Business Accelerator Hub](https://hub.sap.com/api/CE_PURCHASEREQUISITION_0001/overview). <br>
To enable the Purchase Requiistion API, we have already created a **Communication Arrangement** using the Communication Scenario **SAP_COM_0102** in SAP S/4HANA Cloud system with valid **Communication System** and **Inbound Communication**.

To know more about how to create a Communication Arrangement in SAP S/4HANA Cloud system, kindly check the [help documentation link](https://help.sap.com/docs/SAP_QIR_OD/df7051e6890840b8a82754eb65b69a50/106360c995cb4c3fa366b41edd76fb01.html)

<br/>
We have then used the Purchase Requistion API and communication user credentials in Cloud Inregration capapbility of SAP Integration Suite

<br><img src="/intro/intro3/images/S4_Communication_Arrangement.png" width=100% height=100%>

## Summary

You should now be familiar with all the configurations that has been done in SAP S/4Hana Cloud system to enable the Purchase Requistion API call.

Now that you have gone through all the introduction chapters, you should have a clear picture of the overall integration scenario and the pre-configuration steps that has been performed on the systems
You can now start with the actual exercises. For this, you can navigate to - [Exercise overview section](/README.md#exercises)
