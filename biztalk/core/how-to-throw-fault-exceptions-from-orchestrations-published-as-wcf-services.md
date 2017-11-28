---
title: "作为 WCF 服务如何支持业务流程引发错误异常发布 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, WCF services
- WCF services, orchestrations
- WCF services, errors
- orchestrations, WCF services
ms.assetid: 89f57841-d40e-4a5a-90a8-5556a2766c03
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bf64501f619e74991fafa59b2ab1c2a3e62cbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a><span data-ttu-id="d6dfd-102">如何从发布为 WCF Services 的业务流程中引发错误异常</span><span class="sxs-lookup"><span data-stu-id="d6dfd-102">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>
<span data-ttu-id="d6dfd-103">可以从业务流程发送两种类型的 SOAP 错误的： 类型化和非类型化的 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="d6dfd-103">Two types of SOAP faults can be sent from an orchestration: typed and untyped SOAP faults.</span></span> <span data-ttu-id="d6dfd-104">类型化的 SOAP 错误是指某个操作具有**System.ServiceModel.FaultContractAttribute** ，它指定自定义的 SOAP 错误类型。</span><span class="sxs-lookup"><span data-stu-id="d6dfd-104">Typed SOAP faults are those in which an operation has a **System.ServiceModel.FaultContractAttribute** that specifies a custom SOAP fault type.</span></span> <span data-ttu-id="d6dfd-105">非类型化 SOAP 错误则是那些没有在操作的约定中指定的错误。</span><span class="sxs-lookup"><span data-stu-id="d6dfd-105">Untyped SOAP faults are those that are not specified in the contract for an operation.</span></span>  
  
 <span data-ttu-id="d6dfd-106">WCF 适配器不支持对发布为 WCF Services 的业务流程的类型化错误约定异常进行处理。</span><span class="sxs-lookup"><span data-stu-id="d6dfd-106">WCF adapters do not support processing typed fault contract exceptions for orchestrations published as WCF services.</span></span> <span data-ttu-id="d6dfd-107">但是，非类型化 SOAP 错误可始终由业务流程或管道返回。</span><span class="sxs-lookup"><span data-stu-id="d6dfd-107">However, untyped SOAP faults can always be returned by orchestrations or pipelines.</span></span> <span data-ttu-id="d6dfd-108">若要返回非类型化的 SOAP 错误，你需要设置**System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**上接收位置，或在配置文件中，以允许 WCF 客户端获取信息有关内部服务操作异常。</span><span class="sxs-lookup"><span data-stu-id="d6dfd-108">To return an untyped SOAP fault, you need to set the **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults** on the receive location, or in the config file, to permit WCF clients to obtain information about internal service operation exceptions.</span></span>  
  
 <span data-ttu-id="d6dfd-109">下面的代码演示如何在配置文件中设置该属性：</span><span class="sxs-lookup"><span data-stu-id="d6dfd-109">The following code shows how to set the property in a config file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="ServiceBehaviorConfiguration">  
                    <serviceDebug includeExceptionDetailInFaults="true" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6dfd-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6dfd-110">See Also</span></span>  
 [<span data-ttu-id="d6dfd-111">如何处理在业务流程中的类型化的错误协定</span><span class="sxs-lookup"><span data-stu-id="d6dfd-111">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)