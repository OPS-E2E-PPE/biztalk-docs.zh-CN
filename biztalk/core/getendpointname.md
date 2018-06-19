---
title: GetEndpointName |Microsoft 文档
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
ms.openlocfilehash: e7e7a310c222cead89efd23e3f8202ade9eb47ab
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968755"
---
# <a name="getendpointname"></a>GetEndpointName
将当前侦听终结点的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前侦听终结点名称的字符串。  
  
## <a name="remarks"></a>注释  
 请务必注意，对于在 App.config 文件中指定的相同终结点名称，客户端和服务器应用程序将返回不同的名称。  
  
 对于客户端应用程序，GetEndPointName 操作检索到的终结点名称是后跟下划线和约定名称的绑定名称。  
  
 例如，如果未设置 ServiceEndpoint 上的名称属性，但设置绑定，该名称将设置\<*绑定*\>_\<*协定*\>.  
  
 如果未设置的名称和绑定，将名称属性设置为\<*协定*\>。  
  
 对于服务而言，检索到的名称是在 App.config 文件中指定的终结点名称。  
  
## <a name="example"></a>示例  
 下面的示例筛选器表达式为 PurchaseOrder_EP 终结点的 ServiceRequest 约定调用点的 Receive 操作定义了侦听。 这是通过以下逻辑步骤完成的：  
  
1.  将当前操作名称与“Receive”进行比较，并将结果（True 或 False）推送到堆栈上。  
  
2.  将当前服务约定调用点与“ServiceRequest”进行比较，并将结果（True 或 False）推送到堆栈上。 现在堆栈上有两个布尔值。  
  
3.  比较两个结果的前面的步骤中使用布尔型**和**操作和堆栈上的推送结果。 这样，堆栈上就只剩一个布尔值。  
  
4.  将当前终结点与“PurchaseOrder_EP”进行比较，并将结果（True 或 False）推送到堆栈上。 现在堆栈上有两个布尔值。  
  
5.  最后，将使用一个布尔值在堆栈上的两个布尔值进行比较**和**操作和推送到堆栈的结果。 这会将终结点比较的结果与一个布尔值核对，如果操作名称与约定调用点成功匹配，则此布尔值为 True，否则为 False。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)