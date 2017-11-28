---
title: "加载程序集时出错 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13be3acf6974565c86cc87b14ed58929553d5220
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-loading-assembly"></a><span data-ttu-id="44bae-102">加载程序集时出错</span><span class="sxs-lookup"><span data-stu-id="44bae-102">Error loading assembly</span></span>
## <a name="details"></a><span data-ttu-id="44bae-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="44bae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44bae-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="44bae-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="44bae-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="44bae-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="44bae-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="44bae-106">Event ID</span></span>|<span data-ttu-id="44bae-107">0</span><span class="sxs-lookup"><span data-stu-id="44bae-107">0</span></span>|  
|<span data-ttu-id="44bae-108">事件源</span><span class="sxs-lookup"><span data-stu-id="44bae-108">Event Source</span></span>|<span data-ttu-id="44bae-109">0</span><span class="sxs-lookup"><span data-stu-id="44bae-109">0</span></span>|  
|<span data-ttu-id="44bae-110">组件</span><span class="sxs-lookup"><span data-stu-id="44bae-110">Component</span></span>|<span data-ttu-id="44bae-111">0</span><span class="sxs-lookup"><span data-stu-id="44bae-111">0</span></span>|  
|<span data-ttu-id="44bae-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="44bae-112">Symbolic Name</span></span>|<span data-ttu-id="44bae-113">0</span><span class="sxs-lookup"><span data-stu-id="44bae-113">0</span></span>|  
|<span data-ttu-id="44bae-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="44bae-114">Message Text</span></span>|<span data-ttu-id="44bae-115">此错误指示该位置不可以是完全受信任是否在网络共享上。</span><span class="sxs-lookup"><span data-stu-id="44bae-115">This error indicates the location may not be fully trusted if it is on a network share.</span></span> <span data-ttu-id="44bae-116">检查区域的代码访问安全策略。</span><span class="sxs-lookup"><span data-stu-id="44bae-116">Check the Code Access Security policy for the Zone.</span></span> <span data-ttu-id="44bae-117">或者，文件可能不是 BizTalk .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="44bae-117">Or the file may not be a BizTalk .NET assembly.</span></span> <span data-ttu-id="44bae-118">检查的程序集 [程序集： BizTalkAssembly] 自定义属性。</span><span class="sxs-lookup"><span data-stu-id="44bae-118">Check the assembly for the [assembly: BizTalkAssembly] custom attribute.</span></span> <span data-ttu-id="44bae-119">或者，文件可能不是 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="44bae-119">Or the file may not be a .NET assembly.</span></span> <span data-ttu-id="44bae-120">如果文件是 .dll 或 exe，则可能为非托管代码</span><span class="sxs-lookup"><span data-stu-id="44bae-120">If the file is a .dll or  exe, it may be unmanaged code</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44bae-121">解释</span><span class="sxs-lookup"><span data-stu-id="44bae-121">Explanation</span></span>  
 <span data-ttu-id="44bae-122">此错误指示该位置不可以是完全受信任是否在网络共享上。</span><span class="sxs-lookup"><span data-stu-id="44bae-122">This error indicates the location may not be fully trusted if it is on a network share.</span></span> <span data-ttu-id="44bae-123">检查区域的代码访问安全策略。</span><span class="sxs-lookup"><span data-stu-id="44bae-123">Check the Code Access Security policy for the Zone.</span></span> <span data-ttu-id="44bae-124">或者，文件可能不是 BizTalk .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="44bae-124">Or the file may not be a BizTalk .NET assembly.</span></span> <span data-ttu-id="44bae-125">检查的程序集 [*程序集： BizTalkAssembly*] 自定义属性。</span><span class="sxs-lookup"><span data-stu-id="44bae-125">Check the assembly for the [*assembly: BizTalkAssembly*] custom attribute.</span></span> <span data-ttu-id="44bae-126">或者，文件可能不是 .NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="44bae-126">Or the file may not be a .NET assembly.</span></span> <span data-ttu-id="44bae-127">如果文件是 .dll 或 exe，则可能为非托管代码。</span><span class="sxs-lookup"><span data-stu-id="44bae-127">If the file is a .dll or  exe, it may be unmanaged code.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44bae-128">用户操作</span><span class="sxs-lookup"><span data-stu-id="44bae-128">User Action</span></span>  
 <span data-ttu-id="44bae-129">如果位置的来源可靠，则为其授予完全信任级别。</span><span class="sxs-lookup"><span data-stu-id="44bae-129">Grant Full trust level to the location if it’s from a reliable source.</span></span>  <span data-ttu-id="44bae-130">确保 dll 是有效的 BizTalk .net 程序集。</span><span class="sxs-lookup"><span data-stu-id="44bae-130">Ensure the dll is a valid BizTalk .net assembly.</span></span>