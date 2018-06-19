---
title: 连接 |Microsoft 文档
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
ms.openlocfilehash: 4766f65fb0cbe26c8f3c545c38235d83abb283a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231693"
---
# <a name="concatenate"></a>连接
删除堆栈最上方的两项，连接这两项，然后将结果推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a>Parameters  
 堆栈最上方的两项。  
  
## <a name="pushed-value"></a>推送的值  
 连接操作的字符串结果。  
  
## <a name="remarks"></a>注释  
  
## <a name="example"></a>示例  
 在下面的示例更新表达式，常量字符串"启动:"是"EventTime"上下文属性的值连接在一起并保存到数据库列 NewOrderCreateTime。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [拦截器操作](../core/interceptor-operations.md)