---
title: "GetServiceContractCallPoint |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e291bcf733129991f6d3b5000ca8e9bc1353057
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getservicecontractcallpoint"></a>GetServiceContractCallPoint
推送到堆栈的当前服务协定调用点的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前协定调用点字符串。  
  
## <a name="remarks"></a>注释  
 Windows Communication Framework 的服务可以截获的不同位置中的生存期内的服务协定中。 这些位置可由`System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint`枚举：  
  
|协定调用点|Description|  
|-------------------------|-----------------|  
|ClientReply|客户端答复调用点。|  
|ClientRequest|客户端请求调用点。|  
|ClientFault|客户端故障点。|  
|ServiceReply|服务答复调用点。|  
|serviceRequest|服务请求调用点。|  
|ServiceFault|服务故障点。|  
|CallbackRequest|回调请求调用点。|  
|CallbackReply|回调答复调用点。|  
|CallbackFault|回调故障点。|  
  
## <a name="example"></a>示例  
 以下示例包含为在客户端答复状态中查找特定操作（“Receive”）而配置的事件筛选器表达式。 这可通过使用的操作包括组合`GetOperationName`， `GetServiceContractCallPoint`，和逻辑运算。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ClientReply</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>另请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)