---
title: XML 消息的结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bba81-2f2b-41f3-b8b2-c2fb9c15ea5a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4e7501165dca01c81ad43a0e79184f7e5614ae9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295813"
---
# <a name="structure-of-an-xml-message"></a>XML 消息的结构
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中，XML 实例消息是一个有效的 XML 标记层次结构，这些标记共同构成零个或多个 XML 信封和一个或多个 XML 文档。 例如，以下 XML 实例消息由包含单个 XML 文档（以粗体显示）的单个 XML 信封（使用常规字体）组成。  
  
```  
<ns0:envelope xmlns:ns0="http://myEnvelopeNamespaceURI.org">  
    <header>  
        <firstName>John</firstName>  
        <lastName>Scott</lastName>  
    </header>  
    <body>  
        <ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">            <message>Hello</message>        </ns1:document>  
    </body>  
</ns0:envelope>  
```  
  
 可以使用多种方式将 XML 信封和所包含的 XML 文档组合成有效的 XML 实例消息。 本主题的其余部分将介绍这些不同的组合。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XML 消息信封](../core/xml-message-envelopes.md)  
  
-   [嵌套 XML 消息信封](../core/nested-xml-message-envelopes.md)