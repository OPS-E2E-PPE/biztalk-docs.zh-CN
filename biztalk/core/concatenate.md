---
title: 串联 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e21a773d-a9cc-4a6f-b548-46badcd92aab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d47db49e60b95071b48393735b3b4b0e7cee528
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391631"
---
# <a name="concatenate"></a>连接
从堆栈移除的前两个项，将它们，连接，然后将推送到堆栈上的结果。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a>Parameters  
 在堆栈上前两个项。  
  
## <a name="pushed-value"></a>推送的值  
 字符串串联操作的结果。  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 在下面的示例更新表达式中，常量字符串"启动:"与"EventTime"上下文属性的值连接和持久保存到 NewOrderCreateTime 数据库列中。  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>请参阅  
 [侦听器运算](../core/interceptor-operations.md)