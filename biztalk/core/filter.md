---
title: "筛选器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8dad59d-4a47-4794-bbf9-cba02fe7f0bf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efa69998b1782f42d7730744fd88534d26a87835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="filter"></a>“筛选器”
`Filter`元素包含`Expression`计算结果为`true`或`false`并确定当处理或跳过事件。  
  
## <a name="format"></a>格式  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a>注释  
  
## <a name="example"></a>示例  
 下面的示例定义了一个筛选器，当与相应事件相关的工作流的用户密钥等于“DocumentUrl”时，此筛选器的计算结果为 `true`：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [拦截器 OnEvent 元素](../core/interceptor-onevent-element.md)