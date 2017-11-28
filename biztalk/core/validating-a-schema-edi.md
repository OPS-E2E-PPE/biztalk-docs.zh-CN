---
title: "验证架构 (EDI) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6175460-2dcf-4fef-b770-02f0a058bf93
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44cd2672f7ba9be796c1ff802be51324fbfe3256
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-schema-edi"></a><span data-ttu-id="25f34-102">验证架构 (EDI)</span><span class="sxs-lookup"><span data-stu-id="25f34-102">Validating a Schema (EDI)</span></span>
<span data-ttu-id="25f34-103">可以在设计时验证 EDI 架构。</span><span class="sxs-lookup"><span data-stu-id="25f34-103">You can validate an EDI schema at design time.</span></span> <span data-ttu-id="25f34-104">为此，您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 工具扩展。</span><span class="sxs-lookup"><span data-stu-id="25f34-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="25f34-105">验证架构操作会根据 EDI 规则来验证架构。</span><span class="sxs-lookup"><span data-stu-id="25f34-105">The validate-schema operation validates the schema based on EDI rules.</span></span> <span data-ttu-id="25f34-106">无需指定输入消息实例即可验证架构。</span><span class="sxs-lookup"><span data-stu-id="25f34-106">You do not have to designate an input message instance to validate a schema.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25f34-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="25f34-107">Prerequisites</span></span>  
 <span data-ttu-id="25f34-108">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="25f34-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-schema"></a><span data-ttu-id="25f34-109">若要验证架构</span><span class="sxs-lookup"><span data-stu-id="25f34-109">To validate a schema</span></span>  
  
1.  <span data-ttu-id="25f34-110">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="25f34-110">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="25f34-111">向解决方案资源管理器中的此项目添加您要验证的消息架构。</span><span class="sxs-lookup"><span data-stu-id="25f34-111">To the project in Solution Explorer, add the message schema that you want to validate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25f34-112">消息架构下的相应子文件夹位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="25f34-112">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="25f34-113">有关安装的架构文件的信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。</span><span class="sxs-lookup"><span data-stu-id="25f34-113">For information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="25f34-114">无需生成此项目即可验证架构。</span><span class="sxs-lookup"><span data-stu-id="25f34-114">You do not have to build the project to validate a schema.</span></span>  
  
2.  <span data-ttu-id="25f34-115">右键单击解决方案资源管理器中的架构，然后单击**验证架构**。</span><span class="sxs-lookup"><span data-stu-id="25f34-115">Right-click the schema in Solution Explorer, and then click **Validate Schema**.</span></span>  
  
3.  <span data-ttu-id="25f34-116">检查“输出”窗口中是否有指示操作已成功的消息。</span><span class="sxs-lookup"><span data-stu-id="25f34-116">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f34-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25f34-117">See Also</span></span>  
 [<span data-ttu-id="25f34-118">通过使用设计时 XML 工具</span><span class="sxs-lookup"><span data-stu-id="25f34-118">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)