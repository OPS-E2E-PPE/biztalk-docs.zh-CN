---
title: "验证映射 (EDI) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028a152be285bb79f3cd0899b2143e99ef2b6042
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-map-edi"></a><span data-ttu-id="e8ec6-102">验证映射 (EDI)</span><span class="sxs-lookup"><span data-stu-id="e8ec6-102">Validating a Map (EDI)</span></span>
<span data-ttu-id="e8ec6-103">您可以在设计时验证映射。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-103">You can validate a map at design time.</span></span> <span data-ttu-id="e8ec6-104">若要执行此操作，你使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="e8ec6-105">此操作将生成两个文件，一个包含映射的基础 XSLT，另一个包含扩展对象。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-105">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e8ec6-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="e8ec6-106">Prerequisites</span></span>  
 <span data-ttu-id="e8ec6-107">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-map"></a><span data-ttu-id="e8ec6-108">若要验证映射</span><span class="sxs-lookup"><span data-stu-id="e8ec6-108">To validate a map</span></span>  
  
1.  <span data-ttu-id="e8ec6-109">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-109">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="e8ec6-110">对于解决方案资源管理器中的项目，请添加要验证的映射及其输入和输出消息架构。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-110">To the project in Solution Explorer, add the map that you want to validate and its input and output message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8ec6-111">消息架构下的相应子文件夹位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-111">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="e8ec6-112">有关安装的架构文件的详细信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-112">For more information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8ec6-113">您不需要生成项目即可验证映射。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-113">You do not have to build the project to validate a map.</span></span>  
  
2.  <span data-ttu-id="e8ec6-114">右键单击解决方案资源管理器中的映射，然后单击**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-114">Right-click the map in Solution Explorer, and then click **Validate Map**.</span></span>  
  
3.  <span data-ttu-id="e8ec6-115">检查“输出”窗口中是否有指示操作已成功的消息。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-115">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
4.  <span data-ttu-id="e8ec6-116">请注意任何警告，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中已投递**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-116">Note any warnings that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has posted in the **Output** window.</span></span>  
  
5.  <span data-ttu-id="e8ec6-117">在**输出**窗口中，记下名称和输出 XSLT 的路径。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-117">In the **Output** window, note the name and path of the output XSLT.</span></span> <span data-ttu-id="e8ec6-118">该 XSL 文件的指定名称与映射文件的名称相同，但采用 XSL 扩展名。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-118">This XSL file will be given the same name as the map file, but with an XSL extension.</span></span> <span data-ttu-id="e8ec6-119">您可以按住 Ctrl 键并单击链接，以便在 BizTalk 编辑器中显示 XSL 文件。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-119">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
6.  <span data-ttu-id="e8ec6-120">在**输出**窗口中，记下名称和路径的扩展对象 XML。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-120">In the **Output** window, note the name and path of the extension object XML.</span></span> <span data-ttu-id="e8ec6-121">您可以按住 Ctrl 键并单击链接，以便在 BizTalk 编辑器中显示 XSL 文件。</span><span class="sxs-lookup"><span data-stu-id="e8ec6-121">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ec6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8ec6-122">See Also</span></span>  
 [<span data-ttu-id="e8ec6-123">通过使用设计时 XML 工具</span><span class="sxs-lookup"><span data-stu-id="e8ec6-123">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)