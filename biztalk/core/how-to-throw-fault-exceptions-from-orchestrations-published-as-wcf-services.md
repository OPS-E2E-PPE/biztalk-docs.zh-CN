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
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a>如何从发布为 WCF 服务的业务流程引发错误异常
可以从业务流程发送两种类型的 SOAP 错误： 类型化和非类型化 SOAP 错误。 类型化的 SOAP 错误是指某个操作具有**System.ServiceModel.FaultContractAttribute** ，它指定自定义的 SOAP 错误类型。 非类型化的 SOAP 错误是指那些未在操作协定中指定。  
  
 WCF 适配器不支持处理类型化的错误约定异常进行业务流程发布为 WCF 服务。 但是，始终可以通过业务流程或管道返回非类型化的 SOAP 错误。 若要返回非类型化的 SOAP 错误，您需要设置**System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults**上该接收位置，或在配置文件中，若要允许 WCF 客户端获取信息有关内部服务操作异常。  
  
 下面的代码演示如何在配置文件中设置属性：  
  
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
  
## <a name="see-also"></a>请参阅  
 [如何处理业务流程中的类型化的错误协定](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)