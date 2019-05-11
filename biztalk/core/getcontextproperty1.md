---
title: GetContextProperty1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8867c29-63de-4a13-9ef9-8c6ab8ea3443
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58e843a8324526e183a577425a015b49c7be3725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345133"
---
# <a name="getcontextproperty"></a>GetContextProperty
将推送到堆栈上的请求的上下文属性。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 以下上下文属性名称之一：  
  
|上下文属性名称|Description|  
|---------------------------|-----------------|  
|EventTime|当前日期和时间。|  
|SessionId|工作流会话 id。|  
  
> [!NOTE]
>  上下文属性名称不区分大小写。  
  
## <a name="pushed-value"></a>推送的值  
 包含请求的上下文属性的字符串。  
  
## <a name="remarks"></a>备注  
 时间是 UTC 格式存储在数据库内。  
  
## <a name="example"></a>示例  
 在以下示例更新表达式中，通过检索当前事件的事件时间检索审核日期。  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 这是常见用法的`GetContextProperty`。  
  
## <a name="see-also"></a>请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)