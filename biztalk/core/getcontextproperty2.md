---
title: GetContextProperty2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2554a210-cfb4-4b63-9afa-ffe2a853ba7b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec2f155b9fdb1cf79419531cc7ec2d3e8b87c791
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387703"
---
# <a name="getcontextproperty"></a>GetContextProperty
将推送到堆栈上的请求的上下文属性。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetContextProperty">  
  <wf:Argument>ContextPropertyName</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 以下上下文属性名称之一：  
  
|上下文属性名称|Description|  
|---------------------------|-----------------|  
|EventTime|当前日期和时间。|  
|InstanceId|工作流实例 id。|  
  
> [!NOTE]
>  上下文属性名称不区分大小写。  
  
## <a name="pushed-value"></a>推送的值  
 包含请求的上下文属性的字符串。  
  
## <a name="remarks"></a>备注  
 时间是 UTC 格式存储在数据库内。  
  
## <a name="example"></a>示例  
 在以下示例中，一个表达式，以便拉取**InstanceId**在 correlationID 块内部中用于设置关联 id。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>InstanceId</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 这是常见用法的`GetContextProperty`。