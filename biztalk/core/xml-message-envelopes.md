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
ms.openlocfilehash: 8276e2986231c391479112b25e01bea778566093
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246412"
---
# <a name="xml-message-envelopes"></a>XML 消息信封
在由 Microsoft 发送和接收的 XML 实例消息中的两个用途，XML 信封具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
- XML 信封可包含补充 XML 文档中的数据的数据。 此数据可以升级到消息上下文中，XML 拆装器以便更容易访问不同的 BizTalk Server 组件。 对于出站 XML 实例消息，XML 组装器可以将值从消息上下文降级到信封中，以包含在实例消息传输。  
  
- XML 信封可以用于将多个 XML 文档合并到单个有效的 XML 实例消息。 如果不使用信封来包装到单个根标记中的多个文档，包含多个文档的 XML 实例消息将不适合作为格式正确的 XML。  
  
  典型的 XML 信封 （以粗体显示） 包含数据和用于分隔 （以常规字体显示），它包含一个或多个 XML 文档的标记。  
  
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
  
 不太常见，但仍然有效，XML 信封 （以粗体显示） 不需要包含任何数据或分隔的 XML 文档 （以常规类型显示），它包含的标记。  
  
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
  
 在这种情况下，XML 信封包含开始和结束信封标记以外的任何内容。  
  
## <a name="see-also"></a>请参阅  
 [嵌套的 XML 消息信封](../core/nested-xml-message-envelopes.md)   
 [XML 消息的结构](../core/structure-of-an-xml-message.md)   
 [如何为信封创建架构](../core/how-to-create-schemas-for-envelopes.md)