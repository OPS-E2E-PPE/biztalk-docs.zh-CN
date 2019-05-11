---
title: 调用中使用 WCF 服务模型的 SAP Bapi |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPIs, invoking by using the WCF service model
- WCF service model, invoking BAPIs
ms.assetid: be3c48d6-2213-4ae5-97f4-634fbc423022
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8742f31d494874f30bbae9c8963c1370e91f484f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373335"
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a>调用中使用 WCF 服务模型的 SAP Bapi
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]作为 Bapi 的图面：  
  
- **RFC 操作**。 在 RFC 节点下显示 Bapi 像任何其他 RFC [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
- **SAP 业务对象的方法**。 作为业务对象的方法，由业务对象中的 BAPI 节点下显示 Bapi [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
  调用 BAPI RFC 操作的形式或作为业务对象方法，每个 BAPI 始终 LUW 上的 SAP 系统的一部分。  
  
  有关如何概述[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持 Bapi，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。  
  
  当使用 WCF 服务模型来调用 Bapi 作为业务对象方法时，每个 SAP 业务对象表示由 WCF 客户端类，该业务对象的 Bapi 表示为客户端上的方法。 可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类的特定业务对象，包含用于每个要在代码中调用的 BAPI 方法。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成.NET 类型来封装由每个 BAPI 的参数和数据类型。 然后，您可以创建此 WCF 客户端类的实例并调用其方法来调用目标 Bapi。  
  
  以下各节演示如何为业务对象的方法调用 Bapi 和讨论如何在 WCF 服务模型中支持 BAPI 事务。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示不同的服务协定，为每个业务对象。 这意味着对于每个业务对象的唯一 WCF 客户端类创建的。 此类的名称基于业务对象类型。 例如对于销售订单的业务对象 （业务对象类型 BUS2032） 中，WCF 客户端类是**BapiBUS2032Client**。 在业务对象中的每个目标 BAPI 表示为生成的 WCF 客户端类中的方法。 在每个方法中：  
  
- SAP 导出参数显示为**出**参数  
  
- SAP 调用参数显示为**ref**参数。  
  
- 如结构复杂 SAP 类型为.NET 类相对应的属性与提供给 SAP 类型的字段。 在以下命名空间中定义这些类： microsoft.lobservices.sap._2007._03.Types.Rfc。  
  
  对于每个业务对象显示 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK，应始终包含在 WCF 客户端中。  
  
  下面的代码显示了一部分为销售订单的业务对象生成的 WCF 客户端类。 此客户端包含用于调用 CREATEFROMDAT2、 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 方法。 为清楚起见已省略构造函数和其他代码。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class BapiBUS2032Client : System.ServiceModel.ClientBase<BapiBUS2032>, BapiBUS2032 {  
  
    // Code has been removed for clarity  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="SALESDOCUMENT">Number of Generated Document</param>  
    /// <param name="BEHAVE_WHEN_ERROR">Error Handling</param>  
    /// …  
    /// <param name="ORDER_TEXT">Texts</param>  
    /// <param name="PARTNERADDRESSES">BAPI Reference Structure for Addresses (Org./Company)</param>  
    /// <param name="RETURN">Return Messages</param>  
    /// <returns></returns>  
    public string CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1X ORDER_HEADER_INX,   
                string SALESDOCUMENTIN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPI_SENDER SENDER,   
                string TESTRUN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPAREX[] EXTENSIONIN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICCARD[] ORDER_CCARD,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUBLB[] ORDER_CFGS_BLOB,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUINS[] ORDER_CFGS_INST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUPRT[] ORDER_CFGS_PART_OF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUCFG[] ORDER_CFGS_REF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUREF[] ORDER_CFGS_REFINST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVAL[] ORDER_CFGS_VALUE,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVK[] ORDER_CFGS_VK,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICOND[] ORDER_CONDITIONS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICONDX[] ORDER_CONDITIONS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITM[] ORDER_ITEMS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITMX[] ORDER_ITEMS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDKEY[] ORDER_KEYS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR[] ORDER_PARTNERS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDL[] ORDER_SCHEDULES_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDLX[] ORDER_SCHEDULES_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDTEXT[] ORDER_TEXT,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN) { ...}  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <param name="WAIT">Using the command `COMMIT AND WAIT`</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_COMMIT(string WAIT) { ... }  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_ROLLBACK() { ... }  
}  
```  
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a>WCF 服务模型中的 BAPI 事务  
 每个 BAPI 是否作为 RFC 或作为业务对象方法，它调用上的 SAP 系统; 是事务 (LUW) 的一部分并通过相同的 SAP 连接接收每个 BAPI 是 SAP 系统上相同的 BAPI 事务的一部分。 SAP 提交或回滚 BAPI 事务，当它收到 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 连接上。 在执行 commit 或 rollback 后，通过连接接收到下一步 BAPI 开始新事务。  
  
 适配器的每个 WCF 通道具有专用的 SAP 连接。 在 WCF 服务模型中，每个 WCF 客户端已是发送到 SAP 系统的已用的发送消息的内部通道。 这意味着使用特定的 WCF 客户端调用 Bapi 是 SAP 系统上的唯一 BAPI 事务的一部分。 使用 WCF 服务模型调用 Bapi 作为业务对象方法时，这会产生一个明显的限制。 由于每个 SAP 业务对象表示由专用的 WCF 客户端类，不能从两个不同的业务对象调用 Bapi，作为同一事务的一部分。 解决此问题的方法是调用作为 RFC 操作 Bapi。 这是因为[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成单个 RFC 操作的 WCF 客户端，因此，使用该客户端调用的所有操作，通过相同的 WCF 通道都发送。  
  
> [!IMPORTANT]
>  如果你想要从同一 BAPI 事务中的不同 SAP 业务对象包括 Bapi，您必须作为 RFC 操作 （使用同一个 WCF 客户端） 调用它们。 不能作为业务对象方法调用它们。  
  
 您调用 BAPI_TRANSACTION_COMMIT 或 BAPI_TRANSACTION_ROLLBACK 提交或回滚 BAPI 事务上的 SAP 系统。 该适配器显示这些两个 Bapi:  
  
- 在作为 RFC 操作的基础节点。  
  
- 在每个业务对象。  
  
  有关如何在适配器上 SAP 支持 BAPI 事务的详细信息，请参阅[sap Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)。  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a>如何创建作为业务对象的方法调用 Bapi 的应用程序  
 本部分提供有关如何为业务对象的方法调用 Bapi 的信息。 应遵循相同的基本过程只不过创建面向 Bapi 作为 RFC 操作的 WCF 客户端并使用它来调用每个 BAPI 作为 RFC 操作调用 Bapi。  
  
 若要创建 BAPI 客户端应用程序，请执行以下步骤。  
  
#### <a name="to-create-an-bapi-client-application"></a>若要创建的 BAPI 客户端应用程序  
  
1. 生成 WCF 客户端类。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 来生成 WCF 客户端类 （或类） 的面向业务对象和你想要的 Bapi。 请务必包括 BAPI_TRANSACTION_COMMIT 和为每个目标业务对象公开的 BAPI_TRANSACTION_ROLLBACK 方法 (Bapi)。 有关如何生成 WCF 客户端的详细信息，请参阅[的 SAP 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
2. 创建生成步骤 1 中的 WCF 客户端类的实例并创建和配置 WCF 客户端。 配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[SAP 系统的配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。 以下代码初始化配置中的销售订单 (BUS2032) SAP 业务对象的 WCF 客户端，并设置为 SAP 系统的凭据。  
  
   ```  
   BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
   bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
   bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. 打开 WCF 客户端。  
  
   ```  
   bapiClient.Open();  
   ```  
  
4. 调用在步骤 2 中创建的 WCF 客户端调用 SAP 系统上相应的 Bapi 中的方法。 可以调用多个 SAP 系统上的 Bapi。  
  
5. 结束的事务：  
  
   1.  调用 BAPI_TRANSACTION_COMMIT 方法来提交该事务。  
  
       ```  
       bapiClient.BAPI_TRANSACTION_COMMIT("X");  
       ```  
  
   2.  调用要回滚事务的 BAPI_TRANSACTION_ROLLBACK 方法。  
  
       ```  
       bapiClient.BAPI_TRANSACTION_ROLLBACK();  
       ```  
  
6. 关闭 WCF 客户端。  
  
   ```  
   bapiClient.Close();   
   ```  
  
### <a name="example"></a>示例  
 下面的示例调用在销售订单的业务对象上 CREATEFROMDAT2 BAPI。 它调用 BAPI 几次，并调用 BAPI_TRANSACTION_COMMIT 提交事务。 如果调用 BAPI 时出错，BAPI_TRANSACTION_ROLLBACK 被调用中要回滚事务的异常处理程序。  
  
 CREATEFROMDAT2 方法采用多个参数;为了简洁起见示例省略了这些。 您可以找到一个示例，演示与 Microsoft 一起提供的示例中的 BAPI 事务[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[SAP 适配器的示例](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This Example demonstrates BAPI transactions. Two sales orders are  
// created using the CREATEFROMDAT2 method of a SAP Business Object.   
// After the orders are created, the BAPI transaction is committed.   
// If an exception occurs when sending the BAPIs, the BAPI transaction is   
// rolled back.  
//   
  
namespace SapBapiTxClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the BAPI client from the generated endpoint configuration.  
  
            BapiBUS2032Client bapiClient = null;  
  
            Console.WriteLine("BAPI transaction sample started");  
            Console.WriteLine("\nCreating business object client");  
  
            try  
            {  
                bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
                bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
                bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the BAPI Client  
                bapiClient.Open();  
  
                ...  
  
                // send first BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters ommitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // send second BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters omitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // Commit BAPI Transaction  
                try  
                {  
                    bapiClient.BAPI_TRANSACTION.Commit();  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
            }  
            catch (ConnectionException cex)  
            {  
                // Get here if problem connecting to the SAP system   
  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                // Get here if the SAP system returns an exception  
  
                Console.WriteLine("Exception occurred on the SAP System");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
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
            // Close the client when finished  
                if (bapiClient != null)  
                {  
                    if (bapiClient.State == CommunicationState.Opened)  
                        bapiClient.Close();  
                    else  
                        bapiClient.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [在 SAP 中的 Bapi 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)