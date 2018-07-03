---
redirect_url: /biztalk/core/using-tibco-rendezvous-send-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 74184590ffff9078caa5a8695ff8b0c392a6a217
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024323"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a><span data-ttu-id="6a698-101">使用来自 TIBCO Rendezvous 的 BizTalk Server 以发送消息</span><span class="sxs-lookup"><span data-stu-id="6a698-101">Using BizTalk Server from TIBCO Rendezvous to Send Messages</span></span>
<span data-ttu-id="6a698-102">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。</span><span class="sxs-lookup"><span data-stu-id="6a698-102">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="6a698-103">您可以指定适配器使用消息上下文属性发送的消息类型：</span><span class="sxs-lookup"><span data-stu-id="6a698-103">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
- <span data-ttu-id="6a698-104">**结构化**: 适配器生成 TIBRVMSG_MSG 结构化的消息，根据从 BizTalk Server 收到的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="6a698-104">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="6a698-105">(\*)</span><span class="sxs-lookup"><span data-stu-id="6a698-105">(\*)</span></span>  
  
  <span data-ttu-id="6a698-106">如果 BizTalk Server 发送字段名称长于 127 个字符的消息，则用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到 TIBCO Rendezvous 的最大字段名称大小（即 127）。</span><span class="sxs-lookup"><span data-stu-id="6a698-106">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
  <span data-ttu-id="6a698-107">如果提供 `reply subject name` 属性，则该属性用于在 TIBCO Rendezvous 消息上设置答复主题。</span><span class="sxs-lookup"><span data-stu-id="6a698-107">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="6a698-108">假设将接收端口设置为侦听回复或将其转发到 BizTalk Server，或者一些其他的 TIBCO Rendezvous 程序负责回复。</span><span class="sxs-lookup"><span data-stu-id="6a698-108">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
  <span data-ttu-id="6a698-109">三联（服务、后台程序、网络）组成传输配置。</span><span class="sxs-lookup"><span data-stu-id="6a698-109">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="6a698-110">空（默认）传输配置导致通过默认传输对象发送消息。</span><span class="sxs-lookup"><span data-stu-id="6a698-110">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
  <span data-ttu-id="6a698-111">如果未指定代码页，则适配器使用 UTF-8 编码（代码页 65001）。</span><span class="sxs-lookup"><span data-stu-id="6a698-111">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="6a698-112">发送器端不支持经过认证的消息。</span><span class="sxs-lookup"><span data-stu-id="6a698-112">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a698-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a698-113">See Also</span></span>  
 <span data-ttu-id="6a698-114">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="6a698-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="6a698-115">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="6a698-115">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)