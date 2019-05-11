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
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a><span data-ttu-id="5e923-101">使用来自 TIBCO Rendezvous 的 BizTalk Server 发送消息</span><span class="sxs-lookup"><span data-stu-id="5e923-101">Using BizTalk Server from TIBCO Rendezvous to Send Messages</span></span>
<span data-ttu-id="5e923-102">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用异步 API (Transport.Send)。</span><span class="sxs-lookup"><span data-stu-id="5e923-102">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="5e923-103">您可以指定适配器使用消息上下文属性发送的消息的类型：</span><span class="sxs-lookup"><span data-stu-id="5e923-103">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
- <span data-ttu-id="5e923-104">**结构化**:适配器生成 TIBRVMSG_MSG 结构化的消息，根据从 BizTalk Server 收到的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="5e923-104">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="5e923-105">(\*)</span><span class="sxs-lookup"><span data-stu-id="5e923-105">(\*)</span></span>  
  
  <span data-ttu-id="5e923-106">如果 BizTalk Server 发送字段名称长度超过 127 个字符的消息，用于 TIBCO Rendezvous 的 BizTalk 适配器会将名称截断到最大字段名称大小适用于 TIBCO Rendezvous 即 127。</span><span class="sxs-lookup"><span data-stu-id="5e923-106">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
  <span data-ttu-id="5e923-107">如果`reply subject name`提供属性，它用于 TIBCO Rendezvous 消息上设置答复主题。</span><span class="sxs-lookup"><span data-stu-id="5e923-107">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="5e923-108">假定的接收端口设置为侦听回复，并将其转发到 BizTalk Server 中，或某些其他 TIBCO Rendezvous 程序负责回复。</span><span class="sxs-lookup"><span data-stu-id="5e923-108">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
  <span data-ttu-id="5e923-109">三元数组 （服务、 守护程序、 网络） 组成传输配置。</span><span class="sxs-lookup"><span data-stu-id="5e923-109">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="5e923-110">一个空 （默认值） 传输配置导致通过默认传输对象发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="5e923-110">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
  <span data-ttu-id="5e923-111">如果代码页处于未指定，则适配器将使用 utf-8 编码 （代码页 65001）。</span><span class="sxs-lookup"><span data-stu-id="5e923-111">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="5e923-112">认证发送器端不支持消息。</span><span class="sxs-lookup"><span data-stu-id="5e923-112">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e923-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e923-113">See Also</span></span>  
 <span data-ttu-id="5e923-114">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="5e923-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="5e923-115">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="5e923-115">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)