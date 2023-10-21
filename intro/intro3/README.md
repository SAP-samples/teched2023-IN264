# SAP S/4Hana Cloud System configuration (for your information only)

As per the scenario, we need to automatically create a **Purchase Requisition (PR)** with the approved equipment list in the **SAP S/4HANA Cloud system**.
<br/>To accomplish this, we will use the Purchase Requisition API of the SAP S/4HANA Cloud system, as documented in the [SAP Business Accelerator Hub](https://hub.sap.com/api/CE_PURCHASEREQUISITION_0001/overview). 

To enable the Purchase Requisition API, we have already created a **Communication Arrangement** using the Communication Scenario **SAP_COM_0102** in the SAP S/4HANA Cloud system with a valid **Communication System** and **Inbound Communication**. 
<br/>We then utilized the Purchase Requisition API and communication user credentials in the Cloud Integration capability of the SAP Integration Suite.

To know more about how to create a Communication Arrangement in SAP S/4HANA Cloud system, kindly check the [help documentation link](https://help.sap.com/docs/SAP_QIR_OD/df7051e6890840b8a82754eb65b69a50/106360c995cb4c3fa366b41edd76fb01.html).

<br><img src="/intro/intro3/images/S4_Communication_Arrangement.png" width=100% height=100%>

## Summary

You should now be familiar with all the configurations that have been done in the SAP S/4Hana Cloud system to enable the Purchase Requisition API call.
<br/>Now that you have gone through all the introductory chapters, you should have a clear picture of the overall integration scenario and the pre-configuration steps that have been performed on the systems.

<br/>You can now proceed with the actual exercises. To do this, navigate to the [Exercises](/README.md#exercises) section.
