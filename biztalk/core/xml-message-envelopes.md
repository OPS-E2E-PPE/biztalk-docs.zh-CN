---
title: XML 消息信封 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d01cd85d-7bf7-49fa-aa25-322213bce066
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f4b60dfbc128baead6b0a1ad38d319ba7b6e8fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972406"
---
# <a name="xml-message-envelopes"></a>XML 消息信封
在由 Microsoft 发送和接收的 XML 实例消息中的两个用途，XML 信封具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- XML 信封可包含用于补充 XML 文档中数据的数据。 XML 拆装器可以将此数据升级成消息上下文，以使其可更方便地被各种 BizTalk Server 组件访问。 对于出站 XML 实例消息，XML 组装器可以将值从消息上下文降级到信封中，以便在实例消息传输中包括这些值。  
  
- 可以使用 XML 信封将多个 XML 文档合并到单个有效的 XML 实例消息中。 如果不使用信封来将多个文档包装到单个根标记中，则不会将包含多个文档的 XML 实例消息认定为格式正确的 XML。  
  
  典型的 XML 信封（以粗体显示）既包含数据，又包含用于分隔其包含的一个或多个 XML 文档（以常规字体显示）的标记。  
  
```  
  
  <envelope fieldAttrib1="..." fieldAttrib2="..." ...>     <fieldElem1>...</fieldElem1>     <fieldElem2>...</fieldElem2>     ...     <body>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</body>    ...</envelope>  
```  
  
 XML 信封（以粗体显示）不必包含任何数据或用于分隔其包含的 XML 文档（以常规类型显示）的标记，这种情况比较少见，但仍然有效。  
  
```  
  
      <envelope>  
    <document1>  
        ...  
    </document1>  
    <document2>  
        ...  
    </document2>  
    ...  
</envelope>  
```  
  
 在这种情况下，XML 信封仅由开始信封标记和结束信封标记组成。  
  
## <a name="see-also"></a>请参阅  
 [嵌套的 XML 消息信封](../core/nested-xml-message-envelopes.md)   
 [XML 消息的结构](../core/structure-of-an-xml-message.md)   
 [如何为信封创建架构](../core/how-to-create-schemas-for-envelopes.md)