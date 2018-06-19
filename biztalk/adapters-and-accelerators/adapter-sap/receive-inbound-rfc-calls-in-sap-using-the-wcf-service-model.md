---
title: 使用 WCF 服务模型的 SAP 中收到入站 RFC 调用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving inbound RFC calls
- RFC calls, receiving inbound using the WCF service model
ms.assetid: 064d70d7-1603-467f-9aba-ecab78a567ff
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a415e3ab0ecbaab8778254d817241e5cafb61a92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218453"
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a>使用 WCF 服务模型的 SAP 中收到入站 RFC 调用
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]可以充当 RFC 服务器以接收 Rfc SAP 系统调用。  
  
 若要接收的入站的 Rfc WCF 服务模型中，你必须：  
  
-   确保 RFC 目标，SAP 系统上不存在。  
  
-   确保 RFC 定义 SAP 系统上。  
  
-   RFC 操作从适配器公开的元数据生成 WCF 服务协定 （接口）。 若要执行此操作，请使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe)。  
  
-   实现此接口从 WCF 服务。 WCF 服务的方法包含所需来处理 RFC 并返回响应适配器的逻辑 (并因此 SAP 系统)。  
  
-   托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。  
  
 以下部分说明如何通过使用从 SAP 系统接收 Rfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a>如何将 RFC 发送到 SAP 适配器 SAP 系统设置  
 你可以从 SAP 系统到发送 RFC 之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须确保满足以下条件 SAP 系统上：  
  
-   RFC 目标[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]必须存在。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自行注册以接收来自 SAP 系统的 Rfc RFC 目标。 提供在 SAP 连接如 SAP 网关主机、 SAP 网关服务和适配器使用注册自己的 SAP 程序 ID URI 中的参数。 有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC、 RFC 目标和发送从 SAP 系统的 RFC](creating-an-rfc-in-an-sap-system.md)。  
  
-   必须在 SAP 系统中定义的 RFC。 你必须创建 SAP 系统定义的 RFC 函数模块。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 SAP 系统上使用 RFC 定义以检索有关 RFC （同时在设计时和在运行时） 的元数据。 有关详细信息请参阅[在 SAP 系统中创建 RFC](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)。  
  
    > [!NOTE]
    >  您必须在 SAP 系统，则为定义 RFC但是实现 RFC 适配器客户端代码中。 RFC 必须定义 SAP 系统上，以便该适配器可以 RFC 来检索元数据。  
  
 下面是源代码的在 RFC 添加两个整数并返回其结果的 SAP 系统上的示例。 该代码通过指定的目标只是调用 RFC。 函数的实现可通过[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]客户端代码。  
  
```  
FUNCTION Z_RFC_SAMPLE_ADD.  
*"---------------------------------------------------------------------*"*"Local interface:  
*"  IMPORTING  
*"     VALUE(X) TYPE  INT4  
*"     VALUE(Y) TYPE  INT4  
*"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
*"  EXPORTING  
*"     VALUE(RESULT) TYPE  INT4  
*"---------------------------------------------------------------------CALL FUNCTION 'Z_RFC_MKD_ADD' DESTINATION DEST  
  EXPORTING X = X  
            Y = Y  
  IMPORTING RESULT = RESULT.  
  
ENDFUNCTION.  
```  
  
## <a name="the-wcf-service-contract-for-an-rfc"></a>RFC WCF 服务协定  
 你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 若要为你想要收到来自 SAP 系统的 Rfc 生成 WCF 服务协定。 以下部分说明的托管的代码类和接口为 Z_RFC_MKD_ADD 操作生成。  
  
### <a name="the-rfc-interface-wcf-service-contract"></a>Rfc 接口 （WCF 服务协定）  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现的单个服务协定，"Rfc"下的所有 RFC 操作。 这意味着，一个接口， **Rfc**，创建所有你想要接收的 RFC 操作。 每个目标 RFC 操作表示为此接口的方法。 每个方法采用单个参数，用于表示此操作，请求消息的消息协定，并返回一个对象，它表示该操作的响应消息的消息协定。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a>请求和响应消息  
 每个 RFC 操作采用一个参数以表示请求消息，返回一个对象，表示响应消息。 请求消息的属性包含的导入和 RFC （输入） 可变参数。 响应消息的属性包含导出和 （输出） 操作的可变参数。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", IsWrapped=true)]  
public partial class Z_RFC_MKD_ADDRequest {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=0)]  
    public string DEST;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=1)]  
    public System.Nullable<int> X;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=2)]  
    public System.Nullable<int> Y;  
  
    public Z_RFC_MKD_ADDRequest() {  
    }  
  
    public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y) {  
        this.DEST = DEST;  
        this.X = X;  
        this.Y = Y;  
    }  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADDResponse", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", IsWrapped=true)]  
public partial class Z_RFC_MKD_ADDResponse {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=0)]  
    public int RESULT;  
  
    public Z_RFC_MKD_ADDResponse() {  
    }  
  
    public Z_RFC_MKD_ADDResponse(int RESULT) {  
        this.RESULT = RESULT;  
    }  
}  
```  
  
### <a name="the-generated-wcf-service"></a>生成的 WCF 服务  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成实现 WCF 服务协定的 WCF 服务 (**Rfc**)。 此类的方法是存根处理。 此类是在单独的文件中生成的。 你可以直接在此类的方法来实现你的代码。  
  
```  
namespace SAPBindingNamespace {  
  
    public class SAPBindingService : Rfc {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
        public virtual Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="how-to-create-an-rfc-server-application"></a>如何创建的 RFC 服务器应用程序  
 若要从 SAP 系统的 Rfc 接收使用 WCF 服务模型，你可以按照中的步骤[与 SAP 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)。 请务必添加服务终结点 （用于创建和实现 WCF 服务过程的步骤 6） 时，服务协定指定 Rfc。  
  
 下面的代码演示如何通过从某个 SAP 系统接收 Z_RFC_MKD_RFC 的完整示例[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 此 RFC 采用两个整数参数，并将结果返回给 SAP 系统。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for the WCF LOB Adapter SDK and SAP adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace SapRfcServerSM  
{  
    // Implement a WCF service callback class by sub-classing the generated service callback class (SAPBindingService).  
    // You must annotate this class with the InstanceContextMode.Single ServiceBehavior  
    // If you implement your code in SAPBindingService.cs be sure to annotate the SAPBindingService class  
    // The callback method should return a Z_RFC_MKD_ADDResponse to indicate successful processing  
    // or throw an exception to indicate an error.  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
    class RfcServerClass : SAPBindingNamespace.SAPBindingService  
    {  
  
        public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
        {  
            // If either parameter is null, throw an exception   
            if (request.X == null || request.Y == null)  
                throw new System.ArgumentNullException();  
  
            int result = (int) (request.X + request.Y);  
  
            Console.WriteLine("\nRfc Received");  
            Console.WriteLine("X =\t\t" + request.X.ToString());  
            Console.WriteLine("Y =\t\t" + request.Y.ToString());  
            Console.WriteLine("Result =\t" + result);  
            Console.WriteLine("\nHit <RETURN> to end");  
  
            return new Z_RFC_MKD_ADDResponse(result);  
        }  
  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Listener connection for the service URI -- the connection URI must contain credentials  
            Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/ADAPSAP47/00?ListenerGwServ=SAPGW00&ListenerGwHost=ADAPSAP47&ListenerProgramId=ADDER");  
  
            // The baseUri cannot contain userinfoparams or query_string parameters  
            Uri[] baseUri = new Uri[] { new Uri("sap://a/ADAPSAP47/00") };  
  
            Console.WriteLine("RFC server sample started");  
  
            // create service instance  
            RfcServerClass rfcServerInstance = new RfcServerClass();  
  
            try  
            {  
                Console.WriteLine("Initializing service host -- please wait");  
                // Create and initialize a service host  
                using (ServiceHost srvHost = new ServiceHost(rfcServerInstance, baseUri))  
                {  
  
                    // Add service endpoint   
                    // Specify AcceptCredentalsInUri=true for the binding  
                    // NOTE: The contract for the service endpoint is "Rfc".  
                    //       This is the generated WCF service callback interface (see SAPBindingInterface.cs).  
                    SAPBinding binding = new SAPBinding();  
                    binding.AcceptCredentialsInUri = true;  
                    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
                    srvHost.Open();  
  
                    Console.WriteLine("\nReady to receive Z_RFC_MKD_ADD RFC");  
                    Console.WriteLine("Hit <RETURN> to end");  
  
                    // Wait to receive request  
                    Console.ReadLine();  
                }  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
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
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)