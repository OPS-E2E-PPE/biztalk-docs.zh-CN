---
title: "默认应用命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe2519fc5507ae0975d050a998faec78f2940a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="listtypes-command"></a><span data-ttu-id="103d1-102">默认应用命令</span><span class="sxs-lookup"><span data-stu-id="103d1-102">ListTypes Command</span></span>
<span data-ttu-id="103d1-103">列出的所有项目类型可添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用**AddResource**命令。</span><span class="sxs-lookup"><span data-stu-id="103d1-103">Lists all of the artifact types that you can add to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the **AddResource** command.</span></span> <span data-ttu-id="103d1-104">有关详细信息**AddResource**命令，请参阅[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="103d1-104">For more information about the **AddResource** command, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
 <span data-ttu-id="103d1-105">受支持的项目类型的完全限定名称如下所示：</span><span class="sxs-lookup"><span data-stu-id="103d1-105">The fully qualified names of the supported artifact types are as follows:</span></span>  
  
-   <span data-ttu-id="103d1-106">.NET 程序集：System.BizTalk:Assembly</span><span class="sxs-lookup"><span data-stu-id="103d1-106">.NET assembly: System.BizTalk:Assembly</span></span>  
  
-   <span data-ttu-id="103d1-107">BAM 定义：System.BizTalk:Bam</span><span class="sxs-lookup"><span data-stu-id="103d1-107">BAM definition: System.BizTalk:Bam</span></span>  
  
-   <span data-ttu-id="103d1-108">BizTalk 程序集：System.BizTalk:BizTalkAssembly</span><span class="sxs-lookup"><span data-stu-id="103d1-108">BizTalk assembly: System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="103d1-109">BizTalk 绑定文件：System.BizTalk:BizTalkBinding</span><span class="sxs-lookup"><span data-stu-id="103d1-109">BizTalk binding file: System.BizTalk:BizTalkBinding</span></span>  
  
-   <span data-ttu-id="103d1-110">安全证书：System.BizTalk:Certificate</span><span class="sxs-lookup"><span data-stu-id="103d1-110">Security certificate: System.BizTalk:Certificate</span></span>  
  
-   <span data-ttu-id="103d1-111">COM 组件：System.BizTalk:Com</span><span class="sxs-lookup"><span data-stu-id="103d1-111">COM component: System.BizTalk:Com</span></span>  
  
-   <span data-ttu-id="103d1-112">特别文件：System.BizTalk:File</span><span class="sxs-lookup"><span data-stu-id="103d1-112">Ad hoc file: System.BizTalk:File</span></span>  
  
-   <span data-ttu-id="103d1-113">后续处理脚本：System.BizTalk:PostProcessingScript</span><span class="sxs-lookup"><span data-stu-id="103d1-113">Postprocessing script: System.BizTalk:PostProcessingScript</span></span>  
  
-   <span data-ttu-id="103d1-114">预处理脚本：System.BizTalk:PreProcessingScript</span><span class="sxs-lookup"><span data-stu-id="103d1-114">Preprocessing script: System.BizTalk:PreProcessingScript</span></span>  
  
-   <span data-ttu-id="103d1-115">策略或规则：System.BizTalk:Rules</span><span class="sxs-lookup"><span data-stu-id="103d1-115">Policy or rule: System.BizTalk:Rules</span></span>  
  
-   <span data-ttu-id="103d1-116">虚拟目录：System.BizTalk:WebDirectory</span><span class="sxs-lookup"><span data-stu-id="103d1-116">Virtual directory: System.BizTalk:WebDirectory</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="103d1-117">为了避免命名空间冲突，应该始终使用完整的类型名称（如 System.BizTalk:Assembly），而不应只使用类型名（如 Assembly）。</span><span class="sxs-lookup"><span data-stu-id="103d1-117">To avoid namespace conflicts, you should always use the full type name (such as System.BizTalk:Assembly) rather than the type name alone (such as Assembly).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="103d1-118">用法</span><span class="sxs-lookup"><span data-stu-id="103d1-118">Usage</span></span>  
 <span data-ttu-id="103d1-119">**BTSTask 默认应用**</span><span class="sxs-lookup"><span data-stu-id="103d1-119">**BTSTask ListTypes**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103d1-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="103d1-120">See Also</span></span>  
 [<span data-ttu-id="103d1-121">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="103d1-121">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)