---
title: "使用 WCF 服务模型的 SAP 中收到入站 RFC 调用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving inbound RFC calls
- RFC calls, receiving inbound using the WCF service model
ms.assetid: 064d70d7-1603-467f-9aba-ecab78a567ff
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a415e3ab0ecbaab8778254d817241e5cafb61a92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="a671d-102">使用 WCF 服务模型的 SAP 中收到入站 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="a671d-102">Receive Inbound RFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="a671d-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]可以充当 RFC 服务器以接收 Rfc SAP 系统调用。</span><span class="sxs-lookup"><span data-stu-id="a671d-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] can act as an RFC server to receive RFCs invoked by a SAP system.</span></span>  
  
 <span data-ttu-id="a671d-104">若要接收的入站的 Rfc WCF 服务模型中，你必须：</span><span class="sxs-lookup"><span data-stu-id="a671d-104">To receive the inbound RFCs in the WCF service model, you must:</span></span>  
  
-   <span data-ttu-id="a671d-105">确保 RFC 目标，SAP 系统上不存在。</span><span class="sxs-lookup"><span data-stu-id="a671d-105">Ensure that an RFC destination exists on the SAP system.</span></span>  
  
-   <span data-ttu-id="a671d-106">确保 RFC 定义 SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="a671d-106">Ensure that the RFC is defined on the SAP system.</span></span>  
  
-   <span data-ttu-id="a671d-107">RFC 操作从适配器公开的元数据生成 WCF 服务协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="a671d-107">Generate a WCF service contract (interface) for the RFC operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="a671d-108">若要执行此操作，请使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="a671d-108">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
-   <span data-ttu-id="a671d-109">实现此接口从 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="a671d-109">Implement a WCF service from this interface.</span></span> <span data-ttu-id="a671d-110">WCF 服务的方法包含所需来处理 RFC 并返回响应适配器的逻辑 (并因此 SAP 系统)。</span><span class="sxs-lookup"><span data-stu-id="a671d-110">The methods of the WCF service contain the logic necessary to process the RFC and return a response to the adapter (and hence the SAP system).</span></span>  
  
-   <span data-ttu-id="a671d-111">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="a671d-111">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
 <span data-ttu-id="a671d-112">以下部分说明如何通过使用从 SAP 系统接收 Rfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a671d-112">The following sections show you how to receive RFCs from the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a><span data-ttu-id="a671d-113">如何将 RFC 发送到 SAP 适配器 SAP 系统设置</span><span class="sxs-lookup"><span data-stu-id="a671d-113">How to Set up the SAP System to Send an RFC to the SAP Adapter</span></span>  
 <span data-ttu-id="a671d-114">你可以从 SAP 系统到发送 RFC 之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须确保满足以下条件 SAP 系统上：</span><span class="sxs-lookup"><span data-stu-id="a671d-114">Before you can send an RFC from the SAP system to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must ensure that the following are true on the SAP system:</span></span>  
  
-   <span data-ttu-id="a671d-115">RFC 目标[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]必须存在。</span><span class="sxs-lookup"><span data-stu-id="a671d-115">An RFC destination for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] must exist.</span></span> <span data-ttu-id="a671d-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自行注册以接收来自 SAP 系统的 Rfc RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="a671d-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] registers itself with an RFC destination to receive RFCs from the SAP system.</span></span> <span data-ttu-id="a671d-117">提供在 SAP 连接如 SAP 网关主机、 SAP 网关服务和适配器使用注册自己的 SAP 程序 ID URI 中的参数。</span><span class="sxs-lookup"><span data-stu-id="a671d-117">You supply parameters in the SAP connection URI such as the SAP Gateway Host, the SAP Gateway Service, and the SAP Program ID that the adapter uses to register itself.</span></span> <span data-ttu-id="a671d-118">有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC、 RFC 目标和发送从 SAP 系统的 RFC](creating-an-rfc-in-an-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="a671d-118">For information about how to setup an RFC destination on SAP, see [Create an RFC, RFC destination, and send an RFC from SAP system](creating-an-rfc-in-an-sap-system.md).</span></span>  
  
-   <span data-ttu-id="a671d-119">必须在 SAP 系统中定义的 RFC。</span><span class="sxs-lookup"><span data-stu-id="a671d-119">The RFC must be defined on the SAP system.</span></span> <span data-ttu-id="a671d-120">你必须创建 SAP 系统定义的 RFC 函数模块。</span><span class="sxs-lookup"><span data-stu-id="a671d-120">You must create a function module that defines the RFC on the SAP system.</span></span> <span data-ttu-id="a671d-121">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 SAP 系统上使用 RFC 定义以检索有关 RFC （同时在设计时和在运行时） 的元数据。</span><span class="sxs-lookup"><span data-stu-id="a671d-121">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the RFC definition on the SAP system to retrieve metadata about the RFC (both at design time and at run time).</span></span> <span data-ttu-id="a671d-122">有关详细信息请参阅[在 SAP 系统中创建 RFC](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="a671d-122">For more information see [Creating an RFC in an SAP System](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a671d-123">您必须在 SAP 系统，则为定义 RFC但是实现 RFC 适配器客户端代码中。</span><span class="sxs-lookup"><span data-stu-id="a671d-123">You must define the RFC on the SAP system; however you implement the RFC in your adapter client code.</span></span> <span data-ttu-id="a671d-124">RFC 必须定义 SAP 系统上，以便该适配器可以 RFC 来检索元数据。</span><span class="sxs-lookup"><span data-stu-id="a671d-124">The RFC must be defined on the SAP system so that the adapter can retrieve metadata for the RFC.</span></span>  
  
 <span data-ttu-id="a671d-125">下面是源代码的在 RFC 添加两个整数并返回其结果的 SAP 系统上的示例。</span><span class="sxs-lookup"><span data-stu-id="a671d-125">The following is an example of the source code on the SAP system for an RFC that adds two integers and returns their result.</span></span> <span data-ttu-id="a671d-126">该代码通过指定的目标只是调用 RFC。</span><span class="sxs-lookup"><span data-stu-id="a671d-126">The code merely calls the RFC through a specified destination.</span></span> <span data-ttu-id="a671d-127">函数的实现可通过[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]客户端代码。</span><span class="sxs-lookup"><span data-stu-id="a671d-127">The implementation of the function is done by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] client code.</span></span>  
  
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
  
## <a name="the-wcf-service-contract-for-an-rfc"></a><span data-ttu-id="a671d-128">RFC WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="a671d-128">The WCF Service Contract for an RFC</span></span>  
 <span data-ttu-id="a671d-129">你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel 元数据实用工具 (svcutil.exe) 若要为你想要收到来自 SAP 系统的 Rfc 生成 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="a671d-129">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the RFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="a671d-130">以下部分说明的托管的代码类和接口为 Z_RFC_MKD_ADD 操作生成。</span><span class="sxs-lookup"><span data-stu-id="a671d-130">The following sections show the managed code classes and interfaces generated for the Z_RFC_MKD_ADD operation.</span></span>  
  
### <a name="the-rfc-interface-wcf-service-contract"></a><span data-ttu-id="a671d-131">Rfc 接口 （WCF 服务协定）</span><span class="sxs-lookup"><span data-stu-id="a671d-131">The Rfc Interface (WCF service contract)</span></span>  
 <span data-ttu-id="a671d-132">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]呈现的单个服务协定，"Rfc"下的所有 RFC 操作。</span><span class="sxs-lookup"><span data-stu-id="a671d-132">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="a671d-133">这意味着，一个接口， **Rfc**，创建所有你想要接收的 RFC 操作。</span><span class="sxs-lookup"><span data-stu-id="a671d-133">This means that a single interface, **Rfc**, is created for all of the RFC operations that you want to receive.</span></span> <span data-ttu-id="a671d-134">每个目标 RFC 操作表示为此接口的方法。</span><span class="sxs-lookup"><span data-stu-id="a671d-134">Each target RFC operation is represented as a method of this interface.</span></span> <span data-ttu-id="a671d-135">每个方法采用单个参数，用于表示此操作，请求消息的消息协定，并返回一个对象，它表示该操作的响应消息的消息协定。</span><span class="sxs-lookup"><span data-stu-id="a671d-135">Each method takes a single parameter, which represents the message contract for the request message of the operation, and returns an object, which represents the message contract of the response message of the operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a><span data-ttu-id="a671d-136">请求和响应消息</span><span class="sxs-lookup"><span data-stu-id="a671d-136">The Request and Response Messages</span></span>  
 <span data-ttu-id="a671d-137">每个 RFC 操作采用一个参数以表示请求消息，返回一个对象，表示响应消息。</span><span class="sxs-lookup"><span data-stu-id="a671d-137">Each RFC operation takes a parameter that represents the request message and returns an object that represents the response message.</span></span> <span data-ttu-id="a671d-138">请求消息的属性包含的导入和 RFC （输入） 可变参数。</span><span class="sxs-lookup"><span data-stu-id="a671d-138">The properties of the request message contain the IMPORT and (input) CHANGING parameters of the RFC.</span></span> <span data-ttu-id="a671d-139">响应消息的属性包含导出和 （输出） 操作的可变参数。</span><span class="sxs-lookup"><span data-stu-id="a671d-139">The properties of the response message contain the EXPORT and (output) CHANGING parameters for the operation.</span></span>  
  
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
  
### <a name="the-generated-wcf-service"></a><span data-ttu-id="a671d-140">生成的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="a671d-140">The Generated WCF Service</span></span>  
 <span data-ttu-id="a671d-141">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成实现 WCF 服务协定的 WCF 服务 (**Rfc**)。</span><span class="sxs-lookup"><span data-stu-id="a671d-141">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a WCF service that implements the WCF service contract (**Rfc**).</span></span> <span data-ttu-id="a671d-142">此类的方法是存根处理。</span><span class="sxs-lookup"><span data-stu-id="a671d-142">The methods of this class are stubbed.</span></span> <span data-ttu-id="a671d-143">此类是在单独的文件中生成的。</span><span class="sxs-lookup"><span data-stu-id="a671d-143">This class is generated in a separate file.</span></span> <span data-ttu-id="a671d-144">你可以直接在此类的方法来实现你的代码。</span><span class="sxs-lookup"><span data-stu-id="a671d-144">You can implement your code directly in the methods of this class.</span></span>  
  
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
  
## <a name="how-to-create-an-rfc-server-application"></a><span data-ttu-id="a671d-145">如何创建的 RFC 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="a671d-145">How to Create an RFC Server Application</span></span>  
 <span data-ttu-id="a671d-146">若要从 SAP 系统的 Rfc 接收使用 WCF 服务模型，你可以按照中的步骤[与 SAP 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="a671d-146">To receive RFCs from the SAP system by using the WCF service model, you can follow the steps in [Overview of the WCF Service Model with the SAP Adapter](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md).</span></span> <span data-ttu-id="a671d-147">请务必添加服务终结点 （用于创建和实现 WCF 服务过程的步骤 6） 时，服务协定指定 Rfc。</span><span class="sxs-lookup"><span data-stu-id="a671d-147">Be sure to specify 'Rfc' for the service contract when you add the service endpoint (step 6 of the procedure for creating and implementing a WCF service).</span></span>  
  
 <span data-ttu-id="a671d-148">下面的代码演示如何通过从某个 SAP 系统接收 Z_RFC_MKD_RFC 的完整示例[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a671d-148">The following code shows a complete example of how to receive the Z_RFC_MKD_RFC from an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a671d-149">此 RFC 采用两个整数参数，并将结果返回给 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="a671d-149">This RFC takes two integer parameters and returns the result to the SAP system.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a671d-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a671d-150">See Also</span></span>  
<span data-ttu-id="a671d-151">[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="a671d-151">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="a671d-152">RFC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="a671d-152">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)