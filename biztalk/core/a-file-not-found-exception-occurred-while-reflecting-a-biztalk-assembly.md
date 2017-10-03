---
title: "找不到文件反映 BizTalk 程序集时出现异常 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f13e4539fca9a14e7827afcb092af76e03f8acc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="1d59f-102">反射 BizTalk 程序集时发生异常，未找到某个文件</span><span class="sxs-lookup"><span data-stu-id="1d59f-102">A file not found exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="1d59f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1d59f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d59f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1d59f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1d59f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1d59f-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1d59f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1d59f-106">Event ID</span></span>|<span data-ttu-id="1d59f-107">0</span><span class="sxs-lookup"><span data-stu-id="1d59f-107">0</span></span>|  
|<span data-ttu-id="1d59f-108">事件源</span><span class="sxs-lookup"><span data-stu-id="1d59f-108">Event Source</span></span>|<span data-ttu-id="1d59f-109">0</span><span class="sxs-lookup"><span data-stu-id="1d59f-109">0</span></span>|  
|<span data-ttu-id="1d59f-110">组件</span><span class="sxs-lookup"><span data-stu-id="1d59f-110">Component</span></span>|<span data-ttu-id="1d59f-111">0</span><span class="sxs-lookup"><span data-stu-id="1d59f-111">0</span></span>|  
|<span data-ttu-id="1d59f-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="1d59f-112">Symbolic Name</span></span>|<span data-ttu-id="1d59f-113">0</span><span class="sxs-lookup"><span data-stu-id="1d59f-113">0</span></span>|  
|<span data-ttu-id="1d59f-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="1d59f-114">Message Text</span></span>|<span data-ttu-id="1d59f-115">反射 BizTalk 程序集“{0}”时发生找不到文件的异常。</span><span class="sxs-lookup"><span data-stu-id="1d59f-115">A file not found exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="1d59f-116">如果一个或多个依存关系不可用，则可能发生此问题。</span><span class="sxs-lookup"><span data-stu-id="1d59f-116">This problem may occur if one or more dependencies are not available.</span></span> <span data-ttu-id="1d59f-117">若要更正此问题，请尝试下列选项之一： 1。</span><span class="sxs-lookup"><span data-stu-id="1d59f-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="1d59f-118">将程序集的依存关系复制到同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="1d59f-118">Copy the dependencies of the assembly to the same folder.</span></span> <span data-ttu-id="1d59f-119">2.</span><span class="sxs-lookup"><span data-stu-id="1d59f-119">2.</span></span> <span data-ttu-id="1d59f-120">将缺少的依存关系安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="1d59f-120">Install the missing dependencies into the Global Assembly Cache.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d59f-121">解释</span><span class="sxs-lookup"><span data-stu-id="1d59f-121">Explanation</span></span>  
 <span data-ttu-id="1d59f-122">此错误表明正在发布的 BizTalk 程序集引用了不在全局程序集缓存 (GAC) 或相同目录中的其他程序集。</span><span class="sxs-lookup"><span data-stu-id="1d59f-122">This error indicates the BizTalk Assembly that is being published references another assembly that is not in the Global Assembly Cache (GAC) or in the same directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d59f-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="1d59f-123">User Action</span></span>  
 <span data-ttu-id="1d59f-124">除了错误消息中指定的操作之外，将引用程序集移到全局程序集缓存，或将其复制到与 BizTalk 程序集相同的位置。</span><span class="sxs-lookup"><span data-stu-id="1d59f-124">In addition to the actions specified in the error message, move the reference assembly to the Global Assembly Cache or copy it to the same location as the BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="1d59f-125">单击**启动**，指向**所有程序**，指向 **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** ，然后单击 **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** 。</span><span class="sxs-lookup"><span data-stu-id="1d59f-125">Click **Start**, point to **All Programs**, point to **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**, and then click **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="1d59f-126">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1d59f-126">Open a command prompt.</span></span>  
  
3.  <span data-ttu-id="1d59f-127">浏览到的程序集的位置并输入**gacutil /I /\<***程序集名称***>.dll**</span><span class="sxs-lookup"><span data-stu-id="1d59f-127">Browse to the location of the assembly, and enter **gacutil /I /\<***assembly name***>.dll**</span></span>