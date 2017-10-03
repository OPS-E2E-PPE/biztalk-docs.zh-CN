---
title: "GetContextProperty2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f834bf1271f6706c332123d8b1835e0bd730f069
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getcontextproperty"></a>GetContextProperty
将请求的上下文属性推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 下面的上下文属性名称之一：  
  
|上下文属性名称|Description|  
|---------------------------|-----------------|  
|EventTime|当前日期和时间。|  
|InstanceId|工作流实例 ID。|  
  
> [!NOTE]
>  上下文属性名称区分大小写。  
  
## <a name="pushed-value"></a>推送的值  
 包含请求的上下文属性的字符串。  
  
## <a name="remarks"></a>注释  
 时间以 UTC 格式存储在数据库中。  
  
## <a name="example"></a>示例  
 在下面的示例中，一个表达式，以便拉取**InstanceId** correlationID 块内中用于设置相关 id。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 这是一种常用的`GetContextProperty`。