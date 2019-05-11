---
redirect_url: /biztalk/core/using-tibco-rendezvous-send-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 81e597ead592d001c53c4a360f5d5ca8d3981ac2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401643"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a>使用来自 TIBCO Rendezvous 的 BizTalk Server 发送消息
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。 您可以指定适配器使用消息上下文属性发送的消息的类型：  
  
- **结构化**:适配器生成 TIBRVMSG_MSG 结构化的消息，根据从 BizTalk Server 收到的 XML 数据。 (*)  
  
  如果 BizTalk Server 发送字段名称长度超过 127 个字符的消息，用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到最大字段名称大小适用于 TIBCO Rendezvous 即 127。  
  
  如果`reply subject name`提供属性，它用于 TIBCO Rendezvous 消息上设置答复主题。 假定的接收端口设置为侦听回复，并将其转发到 BizTalk Server 中，或某些其他 TIBCO Rendezvous 程序负责回复。  
  
  三元数组 （服务、 守护程序、 网络） 组成传输配置。 一个空 （默认值） 传输配置导致通过默认传输对象发送一条消息。  
  
  如果代码页处于未指定，则适配器将使用 utf-8 编码 （代码页 65001）。 认证发送器端不支持消息。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)   
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)