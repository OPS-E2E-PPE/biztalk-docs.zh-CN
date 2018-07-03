---
title: 调用中使用 WCF 服务模型的 SAP Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking RFCs, using the WCF service model
- WCF service model, invoking RFCs
ms.assetid: 06a373e2-5d16-4480-81ec-611bd0b9749c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991fec074369e774a9eef9ab2ae34f10436c6a4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973694"
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a>调用中使用 WCF 服务模型的 SAP Rfc
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP 系统上的 Rfc 显示为可由客户端程序调用的操作。 在 WCF 服务模型中，为生成的 WCF 客户端类的方法调用这些操作。 可以使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]来生成 WCF 客户端类，它包含你要在代码中调用每个 RFC 的方法。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成.NET 类型来封装由每个 RFC 的参数和数据类型。 然后，您可以创建此 WCF 客户端类的实例并调用其方法来调用目标 Rfc。  
  
 以下部分说明如何使用 SAP 系统上调用 Rfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="the-wcf-client-class"></a>WCF 客户端类  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]单一的服务合同，"Rfc"下的所有 RFC 操作的图都面。 这意味着，单一的 WCF 客户端类， **RfcClient**，为所有你想要调用的 RFC 操作的创建。 每个目标 RFC 表示为此类的方法。 在每个方法中：  
  
- SAP 导出参数显示为**出**参数  
  
- SAP 更改参数显示为**ref**参数。  
  
- 如结构复杂 SAP 类型为.NET 类相对应的属性与提供给 SAP 类型的字段。 在以下命名空间中定义这些类： microsoft.lobservices.sap._2007._03.Types.Rfc。  
  
  下面的代码显示了一部分**RfcClient**类和方法调用 SD_RFC_CUSTOMER_GET SAP 系统上。  
  
```  
 [System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class RfcClient : System.ServiceModel.ClientBase<Rfc>, Rfc {  
  
    ...  
  
    /// <summary>The metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="KUNNR">Customer number</param>  
    /// <param name="NAME1">Name of the customer</param>  
    /// <param name="CUSTOMER_T">Table of the selected customers</param>  
    /// <returns></returns>  
    public void SD_RFC_CUSTOMER_GET(string KUNNR, string NAME1, ref microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] CUSTOMER_T) {...}  
}  
```  
  
## <a name="how-to-create-an-rfc-client-application"></a>如何创建 RFC 客户端应用程序  
 若要创建的 RFC 客户端应用程序，请执行以下步骤。  
  
#### <a name="to-create-an-rfc-client-application"></a>若要创建的 RFC 客户端应用程序  
  
1. 生成**RfcClient**类。 使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 生成**RfcClient**以你想要的 Rfc 目标的类。 有关如何生成 WCF 客户端的详细信息，请参阅[的 SAP 解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
2. 创建的实例**RfcClient**类中生成的步骤 1，并指定客户端绑定。 指定客户端绑定涉及到指定的绑定和终结点地址**RfcClient**将使用。 可以在代码中以强制方式或在配置中以声明方式执行此操作。 有关如何指定客户端绑定的详细信息，请参阅[SAP 系统的配置客户端绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。 下面的代码初始化**RfcClient**从配置和 SAP 系统的凭据集。  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. 打开 WCF 客户端。  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. 调用方法**RfcClient**在步骤 2 来执行 SAP 系统的操作中创建。 下面的代码调用**SD_RFC_CUSTOMER_GET**方法**RfcClient**调用 SAP 系统上的 RFC。  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. 关闭 WCF 客户端。  
  
   ```  
   rfcClient.Close();   
   ```  
  
### <a name="example"></a>示例  
 下面是完整的代码示例调用 SD_RFC_CUSTOMER_GET 返回名称以"AB"开头的客户的列表，然后将名称和 ID 为每个客户写入控制台。 此示例将创建**RfcClient**内**使用**语句。 无需显式关闭**RfcClient**; 的执行路径退出上下文时将关闭。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
namespace SapRfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                // Create client from configuration  
                using (RfcClient rfcClient = new RfcClient("SAPBinding_Rfc"))  
                {  
  
                    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                    // Open client  
                    rfcClient.Open();  
  
                    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers = new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
                    // Invoke SD_RFC_CUSTOMER_GET  
                    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
  
                    // Write the results to the console  
                    foreach (microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST customer in customers)  
                    {  
                        Console.WriteLine("Customer Name = " + customer.NAME1);  
                        Console.WriteLine("         Id   = " + customer.KUNNR);  
                        Console.WriteLine();  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
                if (ex.InnerException != null)  
                    Console.WriteLine("Inner exception is :" + ex.InnerException);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)