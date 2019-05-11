---
title: 筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8dad59d-4a47-4794-bbf9-cba02fe7f0bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5366385056383fd260fb80e2e6fa8b3f842ac48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388002"
---
# <a name="filter"></a>“筛选器”
`Filter`元素包含`Expression`的计算结果为`true`或`false`并确定当处理或跳过事件。  
  
## <a name="format"></a>格式  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 下面的示例定义筛选器的计算结果为`true`当工作流与事件关联的用户密钥等于"DocumentUrl":  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>请参阅  
 [侦听器 OnEvent 元素](../core/interceptor-onevent-element.md)