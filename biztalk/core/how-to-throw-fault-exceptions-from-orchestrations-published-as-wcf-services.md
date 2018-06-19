---
title: 作为 WCF 服务如何支持业务流程引发错误异常发布 |Microsoft 文档
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
ms.openlocfilehash: 9bf64501f619e74991fafa59b2ab1c2a3e62cbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255733"
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a>如何从发布为 WCF Services 的业务流程中引发错误异常
可以从业务流程发送两种类型的 SOAP 错误的： 类型化和非类型化的 SOAP 错误。 类型化的 SOAP 错误是指某个操作具有**System.ServiceModel.FaultContractAttribute** ，它指定自定义的 SOAP 错误类型。 非类型化 SOAP 错误则是那些没有在操作的约定中指定的错误。  
  
 WCF 适配器不支持对发布为 WCF Services 的业务流程的类型化错误约定异常进行处理。 但是，非类型化 SOAP 错误可始终由业务流程或管道返回。 若要返回非类型化的 SOAP 错误，你需要设置**System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**上接收位置，或在配置文件中，以允许 WCF 客户端获取信息有关内部服务操作异常。  
  
 下面的代码演示如何在配置文件中设置该属性：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [如何处理在业务流程中的类型化的错误协定](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)