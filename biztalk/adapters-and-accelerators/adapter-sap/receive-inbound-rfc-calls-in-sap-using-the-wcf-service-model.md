---
title: 在使用 WCF 服务模型的 SAP 中收到的入站 RFC 调用 |Microsoft Docs
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
ms.openlocfilehash: 044969142c39d2844c2d9afd4bfe94ade8eded84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373032"
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="b06ff-102">在使用 WCF 服务模型的 SAP 中收到的入站 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="b06ff-102">Receive Inbound RFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="b06ff-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]可以充当一个 RFC 服务器用于接收 Rfc SAP 系统调用。</span><span class="sxs-lookup"><span data-stu-id="b06ff-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] can act as an RFC server to receive RFCs invoked by a SAP system.</span></span>  
  
 <span data-ttu-id="b06ff-104">若要接收的入站的 Rfc 的 WCF 服务模型中，您必须：</span><span class="sxs-lookup"><span data-stu-id="b06ff-104">To receive the inbound RFCs in the WCF service model, you must:</span></span>  
  
- <span data-ttu-id="b06ff-105">请确保在 SAP 系统上存在的 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="b06ff-105">Ensure that an RFC destination exists on the SAP system.</span></span>  
  
- <span data-ttu-id="b06ff-106">确保 SAP 系统上定义了 RFC。</span><span class="sxs-lookup"><span data-stu-id="b06ff-106">Ensure that the RFC is defined on the SAP system.</span></span>  
  
- <span data-ttu-id="b06ff-107">RFC 操作从由适配器公开的元数据生成 WCF 服务协定 （接口）。</span><span class="sxs-lookup"><span data-stu-id="b06ff-107">Generate a WCF service contract (interface) for the RFC operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="b06ff-108">若要执行此操作，应使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-108">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
- <span data-ttu-id="b06ff-109">实现此接口中的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b06ff-109">Implement a WCF service from this interface.</span></span> <span data-ttu-id="b06ff-110">WCF 服务的方法包含处理 RFC，并返回到适配器的响应所需的逻辑 (并因此 SAP 系统)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-110">The methods of the WCF service contain the logic necessary to process the RFC and return a response to the adapter (and hence the SAP system).</span></span>  
  
- <span data-ttu-id="b06ff-111">托管此 WCF 服务使用服务主机 (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-111">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
  <span data-ttu-id="b06ff-112">以下部分说明如何通过使用从 SAP 系统接收 Rfc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b06ff-112">The following sections show you how to receive RFCs from the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a><span data-ttu-id="b06ff-113">如何设置 SAP 系统将发送到 SAP 适配器的 RFC</span><span class="sxs-lookup"><span data-stu-id="b06ff-113">How to Set up the SAP System to Send an RFC to the SAP Adapter</span></span>  
 <span data-ttu-id="b06ff-114">可以将 RFC 发送到 SAP 系统从之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，必须确保 SAP 系统上满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="b06ff-114">Before you can send an RFC from the SAP system to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must ensure that the following are true on the SAP system:</span></span>  
  
- <span data-ttu-id="b06ff-115">RFC 目标[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]必须存在。</span><span class="sxs-lookup"><span data-stu-id="b06ff-115">An RFC destination for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] must exist.</span></span> <span data-ttu-id="b06ff-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自行注册以接收来自 SAP 系统的 Rfc 的 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="b06ff-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] registers itself with an RFC destination to receive RFCs from the SAP system.</span></span> <span data-ttu-id="b06ff-117">提供在 SAP 连接 URI，例如 SAP 网关主机、 SAP 网关服务和 SAP 程序 ID，则适配器将使用注册自己的参数。</span><span class="sxs-lookup"><span data-stu-id="b06ff-117">You supply parameters in the SAP connection URI such as the SAP Gateway Host, the SAP Gateway Service, and the SAP Program ID that the adapter uses to register itself.</span></span> <span data-ttu-id="b06ff-118">有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC、 RFC 目标和发送从 SAP 系统的 RFC](creating-an-rfc-in-an-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-118">For information about how to setup an RFC destination on SAP, see [Create an RFC, RFC destination, and send an RFC from SAP system](creating-an-rfc-in-an-sap-system.md).</span></span>  
  
- <span data-ttu-id="b06ff-119">必须在 SAP 系统上定义 RFC。</span><span class="sxs-lookup"><span data-stu-id="b06ff-119">The RFC must be defined on the SAP system.</span></span> <span data-ttu-id="b06ff-120">必须创建 SAP 系统定义的 RFC 函数模块。</span><span class="sxs-lookup"><span data-stu-id="b06ff-120">You must create a function module that defines the RFC on the SAP system.</span></span> <span data-ttu-id="b06ff-121">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 系统上使用 RFC 定义来检索有关 RFC （两者均在设计时和运行时） 的元数据。</span><span class="sxs-lookup"><span data-stu-id="b06ff-121">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the RFC definition on the SAP system to retrieve metadata about the RFC (both at design time and at run time).</span></span> <span data-ttu-id="b06ff-122">有关详细信息请参阅[在 SAP 系统中创建 RFC](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-122">For more information see [Creating an RFC in an SAP System](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b06ff-123">您必须在 SAP 系统，则为定义 RFC但是在适配器客户端代码中实现 RFC。</span><span class="sxs-lookup"><span data-stu-id="b06ff-123">You must define the RFC on the SAP system; however you implement the RFC in your adapter client code.</span></span> <span data-ttu-id="b06ff-124">必须在 RFC 上 SAP 系统中定义，以便该适配器可以检索 RFC 的元数据。</span><span class="sxs-lookup"><span data-stu-id="b06ff-124">The RFC must be defined on the SAP system so that the adapter can retrieve metadata for the RFC.</span></span>  
  
  <span data-ttu-id="b06ff-125">下面是源代码的添加两个整数并返回其结果的 RFC SAP 系统上的示例。</span><span class="sxs-lookup"><span data-stu-id="b06ff-125">The following is an example of the source code on the SAP system for an RFC that adds two integers and returns their result.</span></span> <span data-ttu-id="b06ff-126">该代码通过指定的目标只是调用 RFC。</span><span class="sxs-lookup"><span data-stu-id="b06ff-126">The code merely calls the RFC through a specified destination.</span></span> <span data-ttu-id="b06ff-127">函数的实现通过[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]客户端代码。</span><span class="sxs-lookup"><span data-stu-id="b06ff-127">The implementation of the function is done by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] client code.</span></span>  
  
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
  
## <a name="the-wcf-service-contract-for-an-rfc"></a><span data-ttu-id="b06ff-128">RFC WCF 服务约定</span><span class="sxs-lookup"><span data-stu-id="b06ff-128">The WCF Service Contract for an RFC</span></span>  
 <span data-ttu-id="b06ff-129">您使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或 ServiceModel Metadata Utility Tool (svcutil.exe) 为你想要接收来自 SAP 系统的 Rfc 生成 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="b06ff-129">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the RFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="b06ff-130">以下部分说明的托管的代码类和接口为 Z_RFC_MKD_ADD 操作生成的。</span><span class="sxs-lookup"><span data-stu-id="b06ff-130">The following sections show the managed code classes and interfaces generated for the Z_RFC_MKD_ADD operation.</span></span>  
  
### <a name="the-rfc-interface-wcf-service-contract"></a><span data-ttu-id="b06ff-131">Rfc 接口 （WCF 服务约定）</span><span class="sxs-lookup"><span data-stu-id="b06ff-131">The Rfc Interface (WCF service contract)</span></span>  
 <span data-ttu-id="b06ff-132">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]单一的服务合同，"Rfc"下的所有 RFC 操作的图都面。</span><span class="sxs-lookup"><span data-stu-id="b06ff-132">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="b06ff-133">这意味着，单个接口**Rfc**，为所有你想要接收的 RFC 操作的创建。</span><span class="sxs-lookup"><span data-stu-id="b06ff-133">This means that a single interface, **Rfc**, is created for all of the RFC operations that you want to receive.</span></span> <span data-ttu-id="b06ff-134">RFC 操作的每个目标都表示为此接口的方法。</span><span class="sxs-lookup"><span data-stu-id="b06ff-134">Each target RFC operation is represented as a method of this interface.</span></span> <span data-ttu-id="b06ff-135">每个方法采用一个参数，它表示该操作的请求消息的消息约定，并返回一个对象，它表示该操作的响应消息的消息约定。</span><span class="sxs-lookup"><span data-stu-id="b06ff-135">Each method takes a single parameter, which represents the message contract for the request message of the operation, and returns an object, which represents the message contract of the response message of the operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a><span data-ttu-id="b06ff-136">请求和响应消息</span><span class="sxs-lookup"><span data-stu-id="b06ff-136">The Request and Response Messages</span></span>  
 <span data-ttu-id="b06ff-137">每个 RFC 操作采用一个参数以表示请求消息并返回一个对象，表示响应消息。</span><span class="sxs-lookup"><span data-stu-id="b06ff-137">Each RFC operation takes a parameter that represents the request message and returns an object that represents the response message.</span></span> <span data-ttu-id="b06ff-138">请求消息的属性包含导入和 （输入） 更改参数的 RFC。</span><span class="sxs-lookup"><span data-stu-id="b06ff-138">The properties of the request message contain the IMPORT and (input) CHANGING parameters of the RFC.</span></span> <span data-ttu-id="b06ff-139">响应消息的属性包含在导出和 （输出） 操作的更改参数。</span><span class="sxs-lookup"><span data-stu-id="b06ff-139">The properties of the response message contain the EXPORT and (output) CHANGING parameters for the operation.</span></span>  
  
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
  
### <a name="the-generated-wcf-service"></a><span data-ttu-id="b06ff-140">生成的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="b06ff-140">The Generated WCF Service</span></span>  
 <span data-ttu-id="b06ff-141">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]还会生成实现 WCF 服务协定的 WCF 服务 (**Rfc**)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-141">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a WCF service that implements the WCF service contract (**Rfc**).</span></span> <span data-ttu-id="b06ff-142">此类的方法是存根处理。</span><span class="sxs-lookup"><span data-stu-id="b06ff-142">The methods of this class are stubbed.</span></span> <span data-ttu-id="b06ff-143">在单独的文件生成此类。</span><span class="sxs-lookup"><span data-stu-id="b06ff-143">This class is generated in a separate file.</span></span> <span data-ttu-id="b06ff-144">你可以直接在此类方法实现代码。</span><span class="sxs-lookup"><span data-stu-id="b06ff-144">You can implement your code directly in the methods of this class.</span></span>  
  
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
  
## <a name="how-to-create-an-rfc-server-application"></a><span data-ttu-id="b06ff-145">如何创建 RFC 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="b06ff-145">How to Create an RFC Server Application</span></span>  
 <span data-ttu-id="b06ff-146">若要通过使用 WCF 服务模型从 SAP 系统接收 Rfc，可以按照中的步骤[与 SAP 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b06ff-146">To receive RFCs from the SAP system by using the WCF service model, you can follow the steps in [Overview of the WCF Service Model with the SAP Adapter](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md).</span></span> <span data-ttu-id="b06ff-147">请务必添加服务终结点 （用于创建和实现 WCF 服务的过程的步骤 6） 时，服务协定指定 Rfc。</span><span class="sxs-lookup"><span data-stu-id="b06ff-147">Be sure to specify 'Rfc' for the service contract when you add the service endpoint (step 6 of the procedure for creating and implementing a WCF service).</span></span>  
  
 <span data-ttu-id="b06ff-148">下面的代码演示如何使用 Z_RFC_MKD_RFC 接收来自 SAP 系统的完整示例[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b06ff-148">The following code shows a complete example of how to receive the Z_RFC_MKD_RFC from an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b06ff-149">此 RFC 采用两个整数参数并将结果返回到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="b06ff-149">This RFC takes two integer parameters and returns the result to the SAP system.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b06ff-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="b06ff-150">See Also</span></span>  
<span data-ttu-id="b06ff-151">[使用 WCF 服务模型开发应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="b06ff-151">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="b06ff-152">RFC 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="b06ff-152">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)