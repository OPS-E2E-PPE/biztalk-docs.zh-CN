---
title: GetServiceContractCallPoint | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53ebac10c1d690f47ab79c12affa3505b22f2e49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345195"
---
# <a name="getservicecontractcallpoint"></a>GetServiceContractCallPoint
将推送到堆栈上的当前服务约定调用点的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前的约定调用点的字符串。  
  
## <a name="remarks"></a>备注  
 Windows Communication Framework 服务可以在不同时间点截获生存期内的服务协定。 这些位置定义的`System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint`枚举：  
  
|约定调用点|Description|  
|-------------------------|-----------------|  
|ClientReply|客户端答复调用点。|  
|ClientRequest|客户端请求调用点。|  
|ClientFault|客户端故障点。|  
|ServiceReply|服务答复调用点。|  
|ServiceRequest|服务请求调用点。|  
|ServiceFault|服务故障点。|  
|CallbackRequest|回调请求调用点。|  
|CallbackReply|回调答复调用点。|  
|CallbackFault|回调故障点。|  
  
## <a name="example"></a>示例  
 下面的示例包含配置为在客户端答复状态中查找特定操作 ("Receive") 的事件筛选器表达式。 这是通过使用的操作，包括组合`GetOperationName`， `GetServiceContractCallPoint`，和逻辑运算。  
  
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
  
## <a name="see-also"></a>请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)