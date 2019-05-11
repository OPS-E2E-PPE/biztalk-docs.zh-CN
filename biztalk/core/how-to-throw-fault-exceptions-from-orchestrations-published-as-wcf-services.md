---
title: 如何从业务流程引发错误异常发布为 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, WCF services
- WCF services, orchestrations
- WCF services, errors
- orchestrations, WCF services
ms.assetid: 89f57841-d40e-4a5a-90a8-5556a2766c03
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49be352326a789e77d84cb5ecb77fd0f48c5e1f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383694"
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a><span data-ttu-id="74d65-102">如何从发布为 WCF 服务的业务流程引发错误异常</span><span class="sxs-lookup"><span data-stu-id="74d65-102">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>
<span data-ttu-id="74d65-103">可以从业务流程发送两种类型的 SOAP 错误： 类型化和非类型化 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="74d65-103">Two types of SOAP faults can be sent from an orchestration: typed and untyped SOAP faults.</span></span> <span data-ttu-id="74d65-104">类型化的 SOAP 错误是指某个操作具有**System.ServiceModel.FaultContractAttribute** ，它指定自定义的 SOAP 错误类型。</span><span class="sxs-lookup"><span data-stu-id="74d65-104">Typed SOAP faults are those in which an operation has a **System.ServiceModel.FaultContractAttribute** that specifies a custom SOAP fault type.</span></span> <span data-ttu-id="74d65-105">非类型化的 SOAP 错误是指那些未在操作协定中指定。</span><span class="sxs-lookup"><span data-stu-id="74d65-105">Untyped SOAP faults are those that are not specified in the contract for an operation.</span></span>  
  
 <span data-ttu-id="74d65-106">WCF 适配器不支持处理类型化的错误约定异常进行业务流程发布为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="74d65-106">WCF adapters do not support processing typed fault contract exceptions for orchestrations published as WCF services.</span></span> <span data-ttu-id="74d65-107">但是，始终可以通过业务流程或管道返回非类型化的 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="74d65-107">However, untyped SOAP faults can always be returned by orchestrations or pipelines.</span></span> <span data-ttu-id="74d65-108">若要返回非类型化的 SOAP 错误，您需要设置**System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**上该接收位置，或在配置文件中，若要允许 WCF 客户端获取信息有关内部服务操作异常。</span><span class="sxs-lookup"><span data-stu-id="74d65-108">To return an untyped SOAP fault, you need to set the **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults** on the receive location, or in the config file, to permit WCF clients to obtain information about internal service operation exceptions.</span></span>  
  
 <span data-ttu-id="74d65-109">下面的代码演示如何在配置文件中设置属性：</span><span class="sxs-lookup"><span data-stu-id="74d65-109">The following code shows how to set the property in a config file:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74d65-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="74d65-110">See Also</span></span>  
 [<span data-ttu-id="74d65-111">如何处理业务流程中的类型化的错误协定</span><span class="sxs-lookup"><span data-stu-id="74d65-111">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)