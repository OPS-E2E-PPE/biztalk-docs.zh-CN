---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7c45ae5859f8a42a581777b6d5ad870a66d9dc4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399478"
---
# <a name="tibco-rendezvous-limitations"></a>TIBCO Rendezvous Limitations
在 TIBCO Rendezvous 中，不能保证字段名的唯一性。 如果 TIBCO Rendezvous 消息包含两个相同的名称字段，则结果 XML 无效。  
  
 其他限制包括：  
  
-   未提供字段排序功能。  
  
-   根据 TIBCO Rendezvous 文档，使用者名称中不会使用非打印的字符；但是仍可能使用这样的字符。 用于 TIBCO Rendezvous 的 BizTalk 适配器不支持包含这些字符的使用者名称。  
  
-   不支持与后台程序的安全连接。  
  
-   不支持自定义数据类型。  
  
-   传输端不支持经过验证的消息。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)