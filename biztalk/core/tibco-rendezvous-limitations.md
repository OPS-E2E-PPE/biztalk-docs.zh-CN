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
# <a name="tibco-rendezvous-limitations"></a><span data-ttu-id="cc43f-101">TIBCO Rendezvous Limitations</span><span class="sxs-lookup"><span data-stu-id="cc43f-101">TIBCO Rendezvous Limitations</span></span>
<span data-ttu-id="cc43f-102">在 TIBCO Rendezvous 中，不能保证字段名的唯一性。</span><span class="sxs-lookup"><span data-stu-id="cc43f-102">In TIBCO Rendezvous, field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="cc43f-103">如果 TIBCO Rendezvous 消息包含两个相同的名称字段，则结果 XML 无效。</span><span class="sxs-lookup"><span data-stu-id="cc43f-103">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
 <span data-ttu-id="cc43f-104">其他限制包括：</span><span class="sxs-lookup"><span data-stu-id="cc43f-104">Other limitations include the following:</span></span>  
  
-   <span data-ttu-id="cc43f-105">未提供字段排序功能。</span><span class="sxs-lookup"><span data-stu-id="cc43f-105">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="cc43f-106">根据 TIBCO Rendezvous 文档，使用者名称中不会使用非打印的字符；但是仍可能使用这样的字符。</span><span class="sxs-lookup"><span data-stu-id="cc43f-106">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="cc43f-107">用于 TIBCO Rendezvous 的 BizTalk 适配器不支持包含这些字符的使用者名称。</span><span class="sxs-lookup"><span data-stu-id="cc43f-107">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="cc43f-108">不支持与后台程序的安全连接。</span><span class="sxs-lookup"><span data-stu-id="cc43f-108">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="cc43f-109">不支持自定义数据类型。</span><span class="sxs-lookup"><span data-stu-id="cc43f-109">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="cc43f-110">传输端不支持经过验证的消息。</span><span class="sxs-lookup"><span data-stu-id="cc43f-110">Certified Messaging is not supported on the transmit side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc43f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc43f-111">See Also</span></span>  
 <span data-ttu-id="cc43f-112">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="cc43f-112">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="cc43f-113">入门</span><span class="sxs-lookup"><span data-stu-id="cc43f-113">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)