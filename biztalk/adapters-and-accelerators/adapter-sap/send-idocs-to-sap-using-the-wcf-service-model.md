---
title: "将 Idoc 发送到使用 WCF 服务模型的 SAP |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, sending IDOCs to SAP
- IDOCs, sending to SAP by using the WCF service model
ms.assetid: 84077234-b82b-4e88-b858-ce2cb1383fb4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d9d550887271e2ba54d858456347ea85825554e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="send-idocs-to-sap-using-the-wcf-service-model"></a>将 Idoc 发送到 SAP 使用 WCF 服务模型
在内部，[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]将 Idoc 发送到 SAP 系统，通过调用两个以下 Rfc 之一：  
  
-   版本 3 Idoc 的 IDOC_INBOUND_ASYNCHRONOUS。  
  
-   版本 2 Idoc 的 INBOUND_IDOC_PROCESS。  
  
 你可以将 IDOC 发送到适配器中通过调用适当 RFC （或 tRFC）;但是，你还可以使用两个以下操作以将 Idoc 发送到适配器：  
  
-   **SendIdoc**直接在 IDOC 根节点下显示。 SendIdoc 操作将 IDOC 发送到的字符串 （弱类型化） 数据作为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
-   **发送**单独为每个 IDOC 显示。 发送操作将作为强类型数据添加到发送 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
 这些操作确定如何 IDOC 数据发送到适配器，不如何发送到 SAP 系统。 适配器始终会到 SAP 系统的 IDOC 通过使用相应 tRFC 发送。  
  
 因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]发送 IDOC tRFC，发送和 SendIdoc 操作公开用于确认 （提交） IDOC GUID 参数。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]内部映射与 SAP 事务 ID (TID) tRFC 与该键关联此 GUID。 你可以确认在两种方式之一 IDOC:  
  
-   通过使用**AutoConfirmSentIdocs**绑定属性。 如果此绑定属性设置为**true**，适配器自动确认用于将 IDOC 发送 tRFC。  
  
-   通过调用 RfcConfirmTransID。 IDOC 与关联的 GUID 与调用此操作。  
  
 下列各节演示了如何使用 SendIdoc 和发送操作将 Idoc 发送到 SAP 系统。 来帮助你将 IDOC 发送作为 tRFC 的详细信息，请参阅[使用 WCF 服务模型调用在 SAP 中的 tRFCs](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
  
### <a name="the-sendidoc-operation"></a>SendIdoc 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现单个操作 （和服务协定） 以将 IDOC 发送字符串格式。 服务协定的名称是"Idoc"和 WCF 客户端类是**IdocClient**。  
  
 可以使用此客户端将任意 IDOC 发送到 SAP 中。 它包含单个方法**SendIdoc**，采用两个参数：  
  
-   **idocData**是一个字符串，包含 IDOC 数据  
  
-   **guid**是映射到 SAP TID 的 GUID。  
  
 下面的代码演示为 SendIdoc 操作生成的 WCF 客户端。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocClient : System.ServiceModel.ClientBase<Idoc>, Idoc {  
  
    public void SendIdoc(string idocData, ref System.Nullable\<System.Guid\> guid) {…}  
}  
```  
  
### <a name="the-send-operation"></a>发送操作  
 由于发送操作使用强类型数据，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]每个 idoc 呈现一个唯一的服务协定。 为此协定基于 IDOC 类型、 版本、 发行版号和 CIM 类型 （如果适用），将生成的接口 （以及 WCF 客户端类） 的名称。 例如 ORDERS03.v3.620 idoc，接口名为"IdocORDERS03V3R620"和 WCF 客户端类是**IdocORDERS03V3R620Client**。  
  
 必须为每种不同类型的 IDOC 生成唯一的客户端。 此客户端包含单个方法**发送**，采用两个参数：  
  
-   **idocData**是表示强类型 IDOC 数据的类。  
  
-   **guid**是映射到 SAP TID 的 GUID 的字符串表示。  
  
 下面的代码演示为展现 ORDERS03.v3.620 idoc 发送操作生成的 WCF 客户端。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocORDERS03V3R620Client : System.ServiceModel.ClientBase<IdocORDERS03V3R620>, IdocORDERS03V3R620 {  
  
    ...  
  
    public void Send(ORDERS03 idocData, ref string guid) { ... }  
}  
```  
  
## <a name="how-to-create-an-application-to-send-idocs"></a>如何创建应用程序发送到的 Idoc  
 若要将 IDOC 发送到 SAP 系统，执行以下步骤。  
  
#### <a name="to-send-an-idoc-to-an-sap-system"></a>若要将 IDOC 发送到 SAP 系统  
  
1.  生成 WCF 客户端类。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类面向想要 Idoc。 有关如何生成 WCF 客户端的详细信息，请参阅[生成 SAP 解决方案项目关联的 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。 如果你想要显式确认 Idoc，请确保生成 WCF 客户端 RfcConfirmTransID 操作。 在以下节点下找不到操作：  
  
    -   SendIdoc 操作。 下方的 IDOC 节点中。  
  
    -   发送操作。 在对应于目标 IDOC 类型、 版本和版本号的节点。  
  
    -   RfcConfirmTransID 操作。 下方的 TRFC 节点中。  
  
2.  创建在步骤 1 中生成的 WCF 客户端类的实例并指定客户端绑定。 指定客户端绑定涉及到指定的绑定和 WCF 客户端将使用的终结点地址。 可以在代码中以强制方式或配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[为 SAP 系统配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。 下面的代码初始化 （对于发送操作中） 从配置 IdocClient 并设置用于 SAP 系统的凭据。  
  
    ```  
    SAPBinding binding = new SAPBinding();  
  
    // Set endpoint address  
    EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
    // Create client and set credentials  
    idocClient = new IdocClient(binding, endpointAddress);  
    idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
    idocClient.ClientCredentials.UserName.Password = "YourPassword";;  
    ```  
  
3.  如果你想要确认后，SAP 系统 tRFC 的适配器它将发送 IDOC，设置**AutoConfirmSentIdocs**属性绑定到**true**。 在打开 WCF 客户端之前，你必须执行此操作。  
  
    ```  
    // Set AutoConfirmSentIdocs property to true  
    binding.AutoConfirmSentIdocs = true;  
    ```  
  
4.  打开 WCF 客户端。  
  
    ```  
    idocClient.Open();  
    ```  
  
5.  调用在步骤 2 中创建 WCF 客户端以将 IDOC 发送到 SAP 系统上的相应方法。 你可以将的变量传递，其中包含 GUID 或设置为**null**为**guid**参数。 如果不指定 GUID[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]会为该操作生成一个 (**guid**是**ref**参数)。 下面的代码从文件中读取的 IDOC （采用字符串格式），并将其发送到 SAP 系统，通过使用 SendIdoc 操作。  
  
    ```  
    // Read IDOC into string variable  
    using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
    {  
    idocData = reader.ReadToEnd();  
    }  
  
    //Get a new GUID to pass to SendIdoc. You can also assign a null  
    //value to have the adapter generate a GUID.  
    adapterTxGuid = Guid.NewGuid();  
  
    //Invoke SendIdoc on the client to send the IDOC to the SAP system  
    idocClient.SendIdoc(idocData, ref adapterTxGuid);  
    ```  
  
6.  如果您未设置**AutoConfirmSentIdocs**属性绑定到**true** （在步骤 3 中），然后你必须确认 tRFC SAP 系统上的。 若要这样做必须调用**RfcConfirmTransID**方法**TrfcClient** （创建未显示）。 指定在步骤 4 中的参数返回的 GUID。  
  
    ```  
    trfcClient.RfcConfirmTransID(adapterTxGuid);  
    ```  
  
7.  关闭 WCF 客户端 (和**TrfcClient**，如果使用) 完成后 （后完发送到的 Idoc），使用它。  
  
    ```  
    idocClient.Close();   
    ```  
  
### <a name="example"></a>示例  
 下面的示例使用 SendIdoc 方法将 IDOC 发送到 SAP 系统。 从文件，ORDERS03.txt 中读取 IDOC。 此文件包含 ORDERS03。V3.620 IDOC 和附带的示例;但是，SendIdoc 操作可以用于发送任何 IDOC。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This example sends a flat IDOC to the SAP system by using the SendIdoc operation.  
namespace SapIdocStringClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // variable for the IDOC client  
            IdocClient idocClient = null;  
  
            Console.WriteLine("IDOC string client sample started");  
            try  
            {  
                // Variable for the GUID  
                System.Nullable<System.Guid> adapterTxGuid;  
                // string to hold the Idoc data  
                string idocData;  
                // string to hold the SAP transaction ID (TID)  
                string sapTxId;  
  
                // The client can be configured from app.config, but it is   
                // explicitly configured here for demonstration.  
                // set AutoConfirmSentIdocs property to true  
                SAPBinding binding = new SAPBinding();  
                binding.AutoConfirmSentIdocs = true;  
  
                // Set endpoint address  
                EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPServer/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
                // Create client and set credentials  
                idocClient = new IdocClient(binding, endpointAddress);  
                idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
                idocClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the client and send the Idoc  
                idocClient.Open();  
  
                // Read IDOC into string variable  
                using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
                {  
                    idocData = reader.ReadToEnd();  
                }  
  
                //Get a new GUID to pass to SendIdoc. You can also assign a null.  
                //value to have the adapter generate a GUID.  
                adapterTxGuid = Guid.NewGuid();  
  
                //Invoke SendIdoc on the client to send the IDOC to the SAP system.  
                idocClient.SendIdoc(idocData, ref adapterTxGuid);  
  
                // The AutoConfirmSentIdocs binding property is set to true, so there is no need to  
                // confirm the IDOC. If this property is not set to true, you must call the   
                // RfcConfirmTransID method of a TrfcClient with adapterTxGuid to   
                // confirm the transaction on the SAP system.   
  
                // Get SAP tx id from GUID  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid((Guid) adapterTxGuid);  
  
                Console.WriteLine("IDOC sent");  
                Console.WriteLine("The SAP Transaction Id is : " + sapTxId);  
  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // Close the IDOC client  
                if (idocClient != null)  
                {  
                    if (idocClient.State == CommunicationState.Opened)  
                        idocClient.Close();  
                    else  
                        idocClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)