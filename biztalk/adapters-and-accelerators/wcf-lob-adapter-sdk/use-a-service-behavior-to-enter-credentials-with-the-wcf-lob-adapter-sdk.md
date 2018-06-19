---
title: 使用服务行为来输入具有 WCF LOB 适配器 SDK 凭据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b203cfa-6331-4498-b656-8cd8339f8613
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cc494e55aee70a9a441eccbe056f4651448752d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223877"
---
# <a name="use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="34009-102">使用服务行为来输入具有 WCF LOB 适配器 SDK 的凭据</span><span class="sxs-lookup"><span data-stu-id="34009-102">Use a service behavior to enter credentials with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="34009-103">很多时候，适配器使用者将需要将凭据传递给业务系统的目标行。</span><span class="sxs-lookup"><span data-stu-id="34009-103">Many times, adapter consumers will be required to pass credentials to the target line of business system.</span></span> <span data-ttu-id="34009-104">若要提供此功能，你将需要提供 WCF 服务行为。</span><span class="sxs-lookup"><span data-stu-id="34009-104">To provide this functionality, you will need to provide a WCF service behavior.</span></span>  
  
 <span data-ttu-id="34009-105">下面的代码示例演示如何从服务行为。</span><span class="sxs-lookup"><span data-stu-id="34009-105">The following example code demonstrates how to derive a service behavior.</span></span> <span data-ttu-id="34009-106">它将委托到适配器从适配器的使用者获取的凭据。</span><span class="sxs-lookup"><span data-stu-id="34009-106">It delegates the credentials obtained from the consumer of the adapter to the adapter.</span></span> <span data-ttu-id="34009-107">该适配器然后必须使用业务线协议进行身份验证凭据。</span><span class="sxs-lookup"><span data-stu-id="34009-107">The adapter then must use line-of-business protocols to authenticate the credentials.</span></span> <span data-ttu-id="34009-108">一旦凭据进行身份验证，服务可以启动侦听从业务线应用程序的传入事件。</span><span class="sxs-lookup"><span data-stu-id="34009-108">Once the credentials are authenticated, the service can start listening for incoming events from the line of business application.</span></span>  
  
```  
/// <summary>  
/// This class derives from a WCF service behavior.  It is used in the inbound scenario  
/// for the Inbound Service to pass the line-of-business credentials to the adapter using  
/// WCF ClientCredentials class.  
/// </summary>  
public class InboundClientCredentialsServiceBehavior : ClientCredentials, IServiceBehavior  
{  
    public InboundClientCredentialsServiceBehavior() { }  
  
    public InboundClientCredentialsServiceBehavior(InboundClientCredentialsServiceBehavior other)  
         : base(other)  
    {  
    }  
  
    #region IServiceBehavior Members  
  
    public void AddBindingParameters(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
        bindingParameters.Add(this);  
    }  
  
    public void ApplyDispatchBehavior(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase)  
    {  
    }  
  
    public void Validate(ServiceDescription serviceDescription, System.ServiceModel.ServiceHostBase serviceHostBase)  
    {  
    }  
  
    #endregion  
  
    protected override ClientCredentials CloneCore()  
    {  
        return new InboundClientCredentialsServiceBehavior(this);  
    }  
}  
```  
  
 <span data-ttu-id="34009-109">下面的代码示例演示如何使用服务行为来将凭据传递给适配器。</span><span class="sxs-lookup"><span data-stu-id="34009-109">The following example code shows how to use the service behavior to pass credentials to the adapter.</span></span>  
  
```  
// Create a ServiceHost for the EchoServiceImpl type  
// and use the base address from app.config  
ServiceHost host = new ServiceHost(typeof(EchoServiceImpl));  
  
// Set service behavior to pass the line-of-business credentials.  
InboundClientCredentialsServiceBehavior credentialsBehavior = new InboundClientCredentialsServiceBehavior();  
credentialsBehavior.UserName.UserName = "username";  
credentialsBehavior.UserName.Password = "****";  
host.Description.Behaviors.Add(credentialsBehavior);  
  
// Open the ServiceHost to start listening for messages  
host.Open();  
  
Console.WriteLine("The service is ready.");  
Console.WriteLine("Press <ENTER> to terminate service.");  
Console.ReadLine();  
  
// Close the ServiceHost  
host.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="34009-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34009-110">See Also</span></span>  
 [<span data-ttu-id="34009-111">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="34009-111">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)