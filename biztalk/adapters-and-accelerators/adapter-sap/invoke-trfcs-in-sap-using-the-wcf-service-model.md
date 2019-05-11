---
title: 调用 Trfc 在 SAP 中使用 WCF 服务模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking by using the WCF service model
- WCF service model, invoking tRFCs
ms.assetid: 456fa869-2f1a-42e0-adbf-86bfe0876846
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bbea3332657a5071e1f25c26136181a5154adab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373303"
---
# <a name="invoke-trfcs-in-sap-using-the-wcf-service-model"></a>调用 Trfc 在 SAP 中使用 WCF 服务模型
事务性远程函数调用 (Trfc) 保证*一次性*RFC SAP 系统上执行。 您可以调用任何显示的 Rfc[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 tRFC。 调用 tRFC 的 WCF 服务模型中是类似于调用 RFC 具有以下差异：  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Trfc 不同节点 (TRFC) 比 Rfc (RFC) 下的图面。  
  
- tRFC 客户端调用不会返回 SAP 导出和更改参数值。  
  
- tRFC 操作包括映射到 SAP 事务 ID (TID) 的 GUID 参数通过 trfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
- 调用 tRFC 后，必须调用 RfcConfirmTransID 操作以确认 （提交） tRFC SAP 系统上。 直接在 TRFC 节点下显示此操作。  
  
  有关 tRFC 操作和 RfcConfirmTransID 操作的详细信息，请参阅[Trfc 在 SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)。  
  
  以下部分说明如何通过使用调用 Trfc SAP 系统上的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]单一的服务合同，"Trfc"下的所有 tRFC 操作的图都面。 这意味着，单一的 WCF 客户端类， **TrfcClient**，为所有你想要调用 tRFC 操作的创建。 每个目标 tRFC 表示为此类的方法。 为每个方法：  
  
- 如结构复杂 SAP 类型为.NET 类相对应的属性与提供给 SAP 类型的字段。 这些类定义以下命名空间中： **microsoft.lobservices.sap._2007._03.Types.Rfc**。  
  
  下面的代码显示了一部分**TrfcClient**类和 SAP 系统调用 BAPI_SALESORDER_CREATEFROMDAT2 （作为 tRFC) 的方法。 **TransactionalRfcOperationIdentifier**参数包含映射到 SAP TID 的 GUID。 并非所有方法的参数会显示。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class TrfcClient : System.ServiceModel.ClientBase<Trfc>, Trfc {  
  
    ....  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    public void BAPI_SALESORDER_CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
  
                …  
  
               microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN,   
                ref System.Guid TransactionalRfcOperationIdentifier) { ...  }  
}  
```  
  
 下面的代码演示 RfcConfirmTransID 操作生成的方法。 必须确保此方法生成的一部分**TrfcClient**。 TRFC 节点的正下方显示 RfcConfirmTransID 操作。  
  
```  
public void RfcConfirmTransID(System.Guid TransactionalRfcOperationIdentifier) {…}  
```  
  
## <a name="how-to-create-a-trfc-client-application"></a>如何创建 tRFC 客户端应用程序  
 若要创建的应用程序调用 Trfc 的步骤是类似的步骤遵循以调用 Rfc，但存在以下例外：  
  
-   您必须检索 TRFC 节点下的目标操作。  
  
-   您必须检索 RfcConfirmTransID 操作。 这是直接在 TRFC 节点下显示。  
  
-   若要确认 （提交） 上的 SAP 系统的 tRFC 操作，必须调用该 RfcConfirmTransID 操作，并返回该 tRFC 操作的 GUID。  
  
#### <a name="to-create-a-trfc-client-application"></a>若要创建 tRFC 客户端应用程序  
  
1. 生成**TrfcClient**类。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成**TrfcClient**以你想要的 Rfc 目标的类。 有关如何生成 WCF 客户端的详细信息，请参阅[生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。 确保 RfcConfirmTransID 操作包含在**TrfcClient**类。  
  
2. 创建的实例**TrfcClient**类在步骤 1 中生成并指定客户端绑定。 指定客户端绑定涉及到指定的绑定和终结点地址**TrfcClient**将使用。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[SAP 系统的配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。 下面的代码初始化**TrfcClient**从配置和 SAP 系统的凭据集。  
  
   ```  
   TrfcClient trfcClient = new TrfcClient("SAPBinding_Rfc");  
  
   trfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   trfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. 打开**TrfcClient**。  
  
   ```  
   trfcClient.Open();  
   ```  
  
4. 在调用适当的方法**TrfcClient**步骤 2 来调用目标 tRFC 上的 SAP 系统中创建。 可以将传递的变量，其中包含一个 GUID 或包含空 GUID **TransactionalRrcOperationIdentifier**参数。 如果传递一个空的 GUID，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]会为您生成一个。 下面的代码调用 BAPI_SALESORDER_CREATEFROMDAT2 作为 tRFC （显示方法的参数不是所有） 在 SAP 系统上。 指定一个 GUID。  
  
   ```  
   transactionalRfcOperationIdentifier = Guid.NewGuid();  
  
   //invoke RFC_CUSTOMER_GET as a tRFC  
   trfcClient.BAPI_SALESORDER_CREATEFROMDAT2(  
                                   request.BEHAVE_WHEN_ERROR,  
                                   request.BINARY_RELATIONSHIPTYPE,  
                                   request.CONVERT,  
  
                                   ...  
  
                                   ref transactionalRfcOperationIdentifier);  
   ```  
  
5. 若要确认 TID 与 SAP 系统上 tRFC 相关联，请调用**RfcConfirmTransID**方法**TrfcClient**。 指定的步骤 4 中返回的 GUID **TransactionRfcOperationIdentifier**参数。  
  
   ```  
   trfcClient.RfcConfirmTransID(transactionalRfcOperationIdentifier);  
   ```  
  
6. 关闭**TrfcClient**完成后 （在调用所有 Trfc 完成） 后使用它。  
  
   ```  
   trfcClient.Close();   
   ```  
  
### <a name="example"></a>示例  
 下面的示例演示如何调用 tRFC 作为 BAPI_SALESORDER_CREATE。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, the WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This example demonstrates sending BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC. The client has   
// methods to:  
//      send the BAPI (BAPI_SALESORDER_CREATEFROMDAT2)and to  
//      Confirm the transaction (RfcConfirmTransID)  
// An instance of BAPI_SALESORDER_CREATEFROMDAT2Request (generated)   
// is used to format the BAPI before invoking BAPI_SALESORDER_CREATEFROMDAT2. This   
// is not necessary, but is done to make it easier to read the code.  
// tRFC invocations always includes a ref parameter that contains a GUID. You can optionally   
// set this parameter when you invoke the method; however, you must use the value returned by  
// the adapter when you call RfcConfirmTransID to confirm the transaction on the SAP system.   
// You can call the utility method, SAPAdapterUtilities.ConvertGuidToTid, to get the value  
// of the SAP transaction Id from the GUID that the adapter returns.  
namespace SapTrfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            TrfcClient sapTrfcClient = null;  
  
            try  
            {  
                Console.WriteLine("SAP TRFC client sample started");  
                Console.WriteLine("Creating the TRFC client");  
                // Create the SAP Trfc Client from configuration  
                sapTrfcClient = new TrfcClient("SAPBinding_Trfc");  
                sapTrfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                sapTrfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening the TRFC client");  
                // Open the Trfc Client  
                sapTrfcClient.Open();  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                Guid tidGuid = Guid.NewGuid();  
  
                BAPI_SALESORDER_CREATEFROMDAT2Request request = new BAPI_SALESORDER_CREATEFROMDAT2Request();  
  
                request.ORDER_HEADER_IN = new BAPISDHD1();  
                request.ORDER_HEADER_IN.DOC_TYPE = "TA";  
                request.ORDER_HEADER_IN.SALES_ORG = "1000";  
                request.ORDER_HEADER_IN.DISTR_CHAN = "10";  
                request.ORDER_HEADER_IN.DIVISION = "00";  
                request.ORDER_HEADER_IN.SALES_OFF = "1000";  
                request.ORDER_HEADER_IN.REQ_DATE_H = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_DATE = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_NO_C = "Cust PO";  
                request.ORDER_HEADER_IN.CURRENCY = "EUR";  
  
                BAPISDITM[] orderItems = new BAPISDITM[1];  
                orderItems[0] = new BAPISDITM();  
                orderItems[0].MATERIAL = "P-109";  
                orderItems[0].PLANT = "1000";  
                orderItems[0].TARGET_QU = "ST";  
                request.ORDER_ITEMS_IN = orderItems;  
  
                BAPIPARNR[] orderPartners = new BAPIPARNR[1];  
                orderPartners[0] = new microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR();  
                orderPartners[0].PARTN_ROLE = "AG";  
                orderPartners[0].PARTN_NUMB = "0000001390";  
                request.ORDER_PARTNERS = orderPartners;  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                request.TransactionalRfcOperationIdentifier = Guid.NewGuid();  
  
                Console.WriteLine("Invoking BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC");  
  
                //invoke RFC_CUSTOMER_GET as a tRFC  
                sapTrfcClient.BAPI_SALESORDER_CREATEFROMDAT2(request.BEHAVE_WHEN_ERROR,  
                                                                request.BINARY_RELATIONSHIPTYPE,  
                                                                request.CONVERT,  
                                                                request.INT_NUMBER_ASSIGNMENT,  
                                                                request.LOGIC_SWITCH,  
                                                                request.ORDER_HEADER_IN,  
                                                                request.ORDER_HEADER_INX,  
                                                                request.SALESDOCUMENTIN,  
                                                                request.SENDER,  
                                                                request.TESTRUN,  
                                                                request.EXTENSIONIN,  
                                                                request.ORDER_CCARD,  
                                                                request.ORDER_CFGS_BLOB,  
                                                                request.ORDER_CFGS_INST,  
                                                                request.ORDER_CFGS_PART_OF,  
                                                                request.ORDER_CFGS_REF,  
                                                                request.ORDER_CFGS_REFINST,  
                                                                request.ORDER_CFGS_VALUE,  
                                                                request.ORDER_CFGS_VK,  
                                                                request.ORDER_CONDITIONS_IN,  
                                                                request.ORDER_CONDITIONS_INX,  
                                                                request.ORDER_ITEMS_IN,  
                                                                request.ORDER_ITEMS_INX,  
                                                                request.ORDER_KEYS,  
                                                                request.ORDER_PARTNERS,  
                                                                request.ORDER_SCHEDULES_IN,  
                                                                request.ORDER_SCHEDULES_INX,  
                                                                request.ORDER_TEXT,  
                                                                request.PARTNERADDRESSES,  
                                                                request.RETURN,  
                                                                ref request.TransactionalRfcOperationIdentifier);  
  
                string sapTxId = null;  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("BAPI_SALESORDER_CREATEFROMDAT2 Sent");  
                Console.WriteLine("The SAP Transaction Id is " + sapTxId);  
  
                // Invoke the RfcConfirmTransID method to confirm (commit) the transaction on  
                // the SAP system. This step is required to complete the transaction. The SAP  
                // adapter will always return a TranactionalRfcOperationIdentifier, whether   
                // one was supplied in the call or not.  
                sapTrfcClient.RfcConfirmTransID(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("SAP Transaction {0} has been committed", sapTxId);  
  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
                throw;  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw;  
            }  
            finally  
            {  
                // Close the client  
                if (sapTrfcClient != null)  
                {  
                    if (sapTrfcClient.State == CommunicationState.Opened)  
                        sapTrfcClient.Close();  
                    else  
                        sapTrfcClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [在 SAP 中 Trfc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)