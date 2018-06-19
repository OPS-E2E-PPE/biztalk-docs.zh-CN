---
title: GetContextProperty1 |Microsoft 文档
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
ms.openlocfilehash: 65b7ffffe4b21e3317b920ac50cdc27b12d708d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246261"
---
# <a name="getcontextproperty"></a>GetContextProperty
将请求的上下文属性推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name ="GetContextProperty">  
  <wcf:Argument>EventTime</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 下面的上下文属性名称之一：  
  
|上下文属性名称|Description|  
|---------------------------|-----------------|  
|EventTime|当前日期和时间。|  
|SessionId|工作流会话 id。|  
  
> [!NOTE]
>  上下文属性名称区分大小写。  
  
## <a name="pushed-value"></a>推送的值  
 包含请求的上下文属性的字符串。  
  
## <a name="remarks"></a>注释  
 时间以 UTC 格式存储在数据库中。  
  
## <a name="example"></a>示例  
 在下面的示例更新表达式，通过检索当前事件的事件时间检索批准日期。  
  
```  
<ic:Update DataItemName ="Approval Date" Type ="DATETIME">  
  <ic:Expression>  
    <wcf:Operation Name ="GetContextProperty">  
      <wcf:Argument>EventTime</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:Update>  
```  
  
 这是一种常用的`GetContextProperty`。  
  
## <a name="see-also"></a>另请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)