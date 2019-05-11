---
title: GetEndpointName | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e39dc97a5d1b12b2e9978f3833092355a47b0623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345087"
---
# <a name="getendpointname"></a>GetEndpointName
将推送到堆栈上当前侦听终结点的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前侦听终结点名称的字符串。  
  
## <a name="remarks"></a>备注  
 请务必注意，客户端和服务器应用程序将返回不同的名称在 App.config 文件中指定的相同终结点名称。  
  
 对于客户端应用程序，GetEndPointName 操作检索到的终结点名称是绑定名称后跟下划线和协定名称。  
  
 例如，如果未设置 ServiceEndpoint 上的 Name 属性，但设置了绑定，该名称将设置\<*绑定*\>_\<*协定*\>.  
  
 如果未设置名称和绑定，将名称属性设置为\<*协定*\>。  
  
 对于服务，检索到的名称是在 App.config 文件中指定的终结点名称。  
  
## <a name="example"></a>示例  
 下面的示例筛选器表达式定义了侦听 PurchaseOrder_EP 终结点的 ServiceRequest 约定调用点的 Receive 操作。 这是在以下逻辑步骤：  
  
1.  当前操作名称为"Receive"进行比较并推送到堆栈上的结果 （true 或 false）。  
  
2.  比较当前服务约定调用点与"ServiceRequest"，并将结果 （true 或 false） 推送到堆栈上。 在堆栈上现在有两个布尔值。  
  
3.  在前面步骤中使用一个布尔值的结果进行比较**和**操作和在堆栈上的推送结果。 这将使在堆栈上一个布尔值。  
  
4.  比较当前终结点与"PurchaseOrder_EP"，并推送到堆栈上的结果 （true 或 false）。 在堆栈上现在有两个布尔值。  
  
5.  最后，将使用一个布尔值在堆栈上的两个布尔值进行比较**和**操作和推送到堆栈上的结果。 这将检查布尔值，即如果操作名称与约定调用点成功则为 true 的终结点比较的结果匹配，且否则为 false。  
  
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
      <ic:Argument>ServiceRequest</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wcf:Operation Name="GetEndpointName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>PurchaseOrder_EP</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)