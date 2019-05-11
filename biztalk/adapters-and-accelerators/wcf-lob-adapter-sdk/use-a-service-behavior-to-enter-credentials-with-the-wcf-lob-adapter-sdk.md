---
title: 一种服务行为用于输入凭据与 WCF LOB 适配器 SDK |Microsoft Docs
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
ms.openlocfilehash: 446bb6e93336f765560742c070ee55921df42a9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362714"
---
# <a name="use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk"></a>一种服务行为用于输入凭据与 WCF LOB 适配器 SDK
很多时候，适配器使用者将需要将凭据传递给业务系统的目标行。 若要提供此功能，将需要提供一个 WCF 服务行为。  
  
 下面的代码示例演示如何从一种服务行为。 它将委托给适配器从适配器的使用者获取的凭据。 适配器则必须使用的业务协议进行身份验证凭据。 一旦凭据进行身份验证，服务可以开始侦听来自业务线应用程序的传入事件。  
  
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
  
 下面的代码示例演示如何使用服务行为来将凭据传递给适配器。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)