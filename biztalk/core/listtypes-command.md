---
title: ListTypes 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94febe8a-4c1e-4581-a6d1-ef579633e745
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda39d682bfb4649fc22afd892dd13849bfd1b09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380720"
---
# <a name="listtypes-command"></a><span data-ttu-id="b30b6-102">ListTypes 命令</span><span class="sxs-lookup"><span data-stu-id="b30b6-102">ListTypes Command</span></span>
<span data-ttu-id="b30b6-103">列出可以添加到项目类型的所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用**AddResource**命令。</span><span class="sxs-lookup"><span data-stu-id="b30b6-103">Lists all of the artifact types that you can add to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the **AddResource** command.</span></span> <span data-ttu-id="b30b6-104">有关详细信息**AddResource**命令，请参阅[AddResource 命令](../core/addresource-command.md)。</span><span class="sxs-lookup"><span data-stu-id="b30b6-104">For more information about the **AddResource** command, see [AddResource Command](../core/addresource-command.md).</span></span>  
  
 <span data-ttu-id="b30b6-105">受支持的项目类型的完全限定的名称如下所示：</span><span class="sxs-lookup"><span data-stu-id="b30b6-105">The fully qualified names of the supported artifact types are as follows:</span></span>  
  
-   <span data-ttu-id="b30b6-106">.NET 程序集：System.BizTalk:Assembly</span><span class="sxs-lookup"><span data-stu-id="b30b6-106">.NET assembly: System.BizTalk:Assembly</span></span>  
  
-   <span data-ttu-id="b30b6-107">BAM 定义：System.BizTalk:Bam</span><span class="sxs-lookup"><span data-stu-id="b30b6-107">BAM definition: System.BizTalk:Bam</span></span>  
  
-   <span data-ttu-id="b30b6-108">BizTalk 程序集：System.BizTalk:BizTalkAssembly</span><span class="sxs-lookup"><span data-stu-id="b30b6-108">BizTalk assembly: System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="b30b6-109">BizTalk 绑定文件：System.BizTalk:BizTalkBinding</span><span class="sxs-lookup"><span data-stu-id="b30b6-109">BizTalk binding file: System.BizTalk:BizTalkBinding</span></span>  
  
-   <span data-ttu-id="b30b6-110">安全证书：System.BizTalk:Certificate</span><span class="sxs-lookup"><span data-stu-id="b30b6-110">Security certificate: System.BizTalk:Certificate</span></span>  
  
-   <span data-ttu-id="b30b6-111">COM 组件：System.BizTalk:Com</span><span class="sxs-lookup"><span data-stu-id="b30b6-111">COM component: System.BizTalk:Com</span></span>  
  
-   <span data-ttu-id="b30b6-112">特别文件：System.BizTalk:File</span><span class="sxs-lookup"><span data-stu-id="b30b6-112">Ad hoc file: System.BizTalk:File</span></span>  
  
-   <span data-ttu-id="b30b6-113">后续处理脚本：System.BizTalk:PostProcessingScript</span><span class="sxs-lookup"><span data-stu-id="b30b6-113">Postprocessing script: System.BizTalk:PostProcessingScript</span></span>  
  
-   <span data-ttu-id="b30b6-114">预处理脚本：System.BizTalk:PreProcessingScript</span><span class="sxs-lookup"><span data-stu-id="b30b6-114">Preprocessing script: System.BizTalk:PreProcessingScript</span></span>  
  
-   <span data-ttu-id="b30b6-115">策略或规则：System.BizTalk:Rules</span><span class="sxs-lookup"><span data-stu-id="b30b6-115">Policy or rule: System.BizTalk:Rules</span></span>  
  
-   <span data-ttu-id="b30b6-116">虚拟目录：System.BizTalk:WebDirectory</span><span class="sxs-lookup"><span data-stu-id="b30b6-116">Virtual directory: System.BizTalk:WebDirectory</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b30b6-117">若要避免命名空间冲突，始终应而不是类型名称 （如程序集） 中使用的完整类型名称 （如 system.biztalk: assembly)。</span><span class="sxs-lookup"><span data-stu-id="b30b6-117">To avoid namespace conflicts, you should always use the full type name (such as System.BizTalk:Assembly) rather than the type name alone (such as Assembly).</span></span>  
  
## <a name="usage"></a><span data-ttu-id="b30b6-118">用法</span><span class="sxs-lookup"><span data-stu-id="b30b6-118">Usage</span></span>  
 <span data-ttu-id="b30b6-119">**BTSTask ListTypes**</span><span class="sxs-lookup"><span data-stu-id="b30b6-119">**BTSTask ListTypes**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30b6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b30b6-120">See Also</span></span>  
 [<span data-ttu-id="b30b6-121">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="b30b6-121">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)