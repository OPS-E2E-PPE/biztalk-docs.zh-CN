---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 4e4209c75ca52585c0a11141dbe0d9841fa6a5ba
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24016016"
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="97e82-101">适配器中的架构生成</span><span class="sxs-lookup"><span data-stu-id="97e82-101">Schema Generation in the Adapter</span></span>
<span data-ttu-id="97e82-102">TIBCO Rendezvous 系统中没有消息类型存储库。</span><span class="sxs-lookup"><span data-stu-id="97e82-102">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="97e82-103">所有消息构造和解析都在 Rendezvous 应用程序级别隐藏了。</span><span class="sxs-lookup"><span data-stu-id="97e82-103">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="97e82-104">由于这个限制，用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器无法提供架构生成功能。</span><span class="sxs-lookup"><span data-stu-id="97e82-104">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="97e82-105">编写架构</span><span class="sxs-lookup"><span data-stu-id="97e82-105">Writing Schemas</span></span>  
 <span data-ttu-id="97e82-106">你必须编写架构和使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。</span><span class="sxs-lookup"><span data-stu-id="97e82-106">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="97e82-107">架构对于 BizTalk Server 开发工具和 Visual Studio 中的集成都非常重要。</span><span class="sxs-lookup"><span data-stu-id="97e82-107">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="97e82-108">BizTalk Server 开发人员可以选择提供完整架构、最低限要求的架构，或介于二者之间的版本。</span><span class="sxs-lookup"><span data-stu-id="97e82-108">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e82-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97e82-109">See Also</span></span>  
 [<span data-ttu-id="97e82-110">入门</span><span class="sxs-lookup"><span data-stu-id="97e82-110">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)