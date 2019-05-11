---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 04db79d76850bf657dbd45e6c60e6fb7edbf1ffb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396951"
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="f6dca-101">在适配器中的架构生成</span><span class="sxs-lookup"><span data-stu-id="f6dca-101">Schema Generation in the Adapter</span></span>
<span data-ttu-id="f6dca-102">TIBCO Rendezvous 系统不包括消息类型存储库。</span><span class="sxs-lookup"><span data-stu-id="f6dca-102">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="f6dca-103">所有消息构造和分析隐藏在 Rendezvous 应用程序级别的信息。</span><span class="sxs-lookup"><span data-stu-id="f6dca-103">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="f6dca-104">鉴于此限制，用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器不能提供架构生成功能。</span><span class="sxs-lookup"><span data-stu-id="f6dca-104">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="f6dca-105">编写架构</span><span class="sxs-lookup"><span data-stu-id="f6dca-105">Writing Schemas</span></span>  
 <span data-ttu-id="f6dca-106">必须编写一个架构，并使用**添加现有项**在 Visual Studio 中将其导入在业务流程中使用。</span><span class="sxs-lookup"><span data-stu-id="f6dca-106">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="f6dca-107">架构是 BizTalk Server 开发工具和 Visual Studio 中的集成非常重要。</span><span class="sxs-lookup"><span data-stu-id="f6dca-107">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="f6dca-108">BizTalk Server 开发人员可以选择提供完整的架构、 最低要求的架构或二者之间的版本之间。</span><span class="sxs-lookup"><span data-stu-id="f6dca-108">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6dca-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6dca-109">See Also</span></span>  
 [<span data-ttu-id="f6dca-110">入门</span><span class="sxs-lookup"><span data-stu-id="f6dca-110">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)