---
title: 验证映射 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df76eda6ba42d96866cd8d3d8c4904ab2ef14f42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250214"
---
# <a name="validating-a-map-edi"></a><span data-ttu-id="5ca00-102">验证映射 (EDI)</span><span class="sxs-lookup"><span data-stu-id="5ca00-102">Validating a Map (EDI)</span></span>
<span data-ttu-id="5ca00-103">可以在设计时验证映射。</span><span class="sxs-lookup"><span data-stu-id="5ca00-103">You can validate a map at design time.</span></span> <span data-ttu-id="5ca00-104">若要执行此操作，您使用的 XML 工具扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="5ca00-104">To do so, you use the XML Tool extensions to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] environment.</span></span> <span data-ttu-id="5ca00-105">此操作将生成包含基础映射和包含扩展对象的文件的 XSLT 的文件。</span><span class="sxs-lookup"><span data-stu-id="5ca00-105">This operation generates a file containing the underlying XSLT of the map and a file containing extension objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ca00-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="5ca00-106">Prerequisites</span></span>  
 <span data-ttu-id="5ca00-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="5ca00-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-validate-a-map"></a><span data-ttu-id="5ca00-108">若要验证映射</span><span class="sxs-lookup"><span data-stu-id="5ca00-108">To validate a map</span></span>  
  
1. <span data-ttu-id="5ca00-109">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开一个项目。</span><span class="sxs-lookup"><span data-stu-id="5ca00-109">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open a project.</span></span> <span data-ttu-id="5ca00-110">解决方案资源管理器中的项目，添加你想要验证的映射和其输入和输出消息架构。</span><span class="sxs-lookup"><span data-stu-id="5ca00-110">To the project in Solution Explorer, add the map that you want to validate and its input and output message schemas.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5ca00-111">消息架构位于下的相应子文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5ca00-111">The message schemas are located in the appropriate subfolder under the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder.</span></span> <span data-ttu-id="5ca00-112">有关安装架构文件的详细信息，请参阅[如何安装 EDI 架构文件](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)。</span><span class="sxs-lookup"><span data-stu-id="5ca00-112">For more information on installing the schema files, see [How to Install EDI Schema Files](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="5ca00-113">无需生成项目即可验证映射。</span><span class="sxs-lookup"><span data-stu-id="5ca00-113">You do not have to build the project to validate a map.</span></span>  
  
2. <span data-ttu-id="5ca00-114">右键单击解决方案资源管理器中的映射，然后单击**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="5ca00-114">Right-click the map in Solution Explorer, and then click **Validate Map**.</span></span>  
  
3. <span data-ttu-id="5ca00-115">验证在输出窗口，指示操作成功的消息。</span><span class="sxs-lookup"><span data-stu-id="5ca00-115">Verify that there is a message in the Output window indicating that the operation succeeded.</span></span>  
  
4. <span data-ttu-id="5ca00-116">请注意任何警告，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中发布**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="5ca00-116">Note any warnings that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has posted in the **Output** window.</span></span>  
  
5. <span data-ttu-id="5ca00-117">在中**输出**窗口中，记下名称和输出 XSLT 的路径。</span><span class="sxs-lookup"><span data-stu-id="5ca00-117">In the **Output** window, note the name and path of the output XSLT.</span></span> <span data-ttu-id="5ca00-118">该 XSL 文件都有相同的名称与映射文件，但采用 XSL 扩展名。</span><span class="sxs-lookup"><span data-stu-id="5ca00-118">This XSL file will be given the same name as the map file, but with an XSL extension.</span></span> <span data-ttu-id="5ca00-119">可以按 CTRL 并单击链接以在 BizTalk 编辑器中显示 XSL 文件。</span><span class="sxs-lookup"><span data-stu-id="5ca00-119">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
6. <span data-ttu-id="5ca00-120">在中**输出**窗口中，记下名称和扩展对象 XML 的路径。</span><span class="sxs-lookup"><span data-stu-id="5ca00-120">In the **Output** window, note the name and path of the extension object XML.</span></span> <span data-ttu-id="5ca00-121">可以按 CTRL 并单击链接以在 BizTalk 编辑器中显示 XSL 文件。</span><span class="sxs-lookup"><span data-stu-id="5ca00-121">You can press CTRL and click the link to display the XSL file in the BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca00-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ca00-122">See Also</span></span>  
 [<span data-ttu-id="5ca00-123">通过使用设计时 XML 工具</span><span class="sxs-lookup"><span data-stu-id="5ca00-123">Using Design-Time XML Tools</span></span>](../core/using-design-time-xml-tools.md)