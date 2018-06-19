---
title: 项目位置不为空 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db353050-3662-4ab6-8898-4e4d3bd78ac1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de1e1dd381a75f596b4980430ddcc5d6d8982b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278781"
---
# <a name="the-project-location-is-not-empty"></a><span data-ttu-id="4146d-102">项目位置不为空</span><span class="sxs-lookup"><span data-stu-id="4146d-102">The project location is not empty</span></span>
## <a name="details"></a><span data-ttu-id="4146d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4146d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4146d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4146d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4146d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4146d-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="4146d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4146d-106">Event ID</span></span>|<span data-ttu-id="4146d-107">0</span><span class="sxs-lookup"><span data-stu-id="4146d-107">0</span></span>|  
|<span data-ttu-id="4146d-108">事件源</span><span class="sxs-lookup"><span data-stu-id="4146d-108">Event Source</span></span>|<span data-ttu-id="4146d-109">0</span><span class="sxs-lookup"><span data-stu-id="4146d-109">0</span></span>|  
|<span data-ttu-id="4146d-110">组件</span><span class="sxs-lookup"><span data-stu-id="4146d-110">Component</span></span>|<span data-ttu-id="4146d-111">0</span><span class="sxs-lookup"><span data-stu-id="4146d-111">0</span></span>|  
|<span data-ttu-id="4146d-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="4146d-112">Symbolic Name</span></span>|<span data-ttu-id="4146d-113">0</span><span class="sxs-lookup"><span data-stu-id="4146d-113">0</span></span>|  
|<span data-ttu-id="4146d-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="4146d-114">Message Text</span></span>|<span data-ttu-id="4146d-115">项目位置“{0}”不为空。</span><span class="sxs-lookup"><span data-stu-id="4146d-115">The project location "{0}" is not empty.</span></span> <span data-ttu-id="4146d-116">你需要执行下列操作之一： 1。</span><span class="sxs-lookup"><span data-stu-id="4146d-116">You need to do one of the following: 1.</span></span> <span data-ttu-id="4146d-117">选择新的项目中，2 的不同位置。</span><span class="sxs-lookup"><span data-stu-id="4146d-117">Choose a different location for the new project, 2.</span></span> <span data-ttu-id="4146d-118">指定覆盖才能重复使用现有的位置或 3。</span><span class="sxs-lookup"><span data-stu-id="4146d-118">Specify overwrite to reuse the existing location, or 3.</span></span> <span data-ttu-id="4146d-119">手动删除的项目位置的内容。</span><span class="sxs-lookup"><span data-stu-id="4146d-119">Manually delete the contents of the project location.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4146d-120">解释</span><span class="sxs-lookup"><span data-stu-id="4146d-120">Explanation</span></span>  
 <span data-ttu-id="4146d-121">此错误表明尝试发布服务的虚拟目录不为空。</span><span class="sxs-lookup"><span data-stu-id="4146d-121">This error indicates the virtual directory where the service is trying to be published is not empty.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4146d-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="4146d-122">User Action</span></span>  
 <span data-ttu-id="4146d-123">选择覆盖位置以重新使用相同的位置。</span><span class="sxs-lookup"><span data-stu-id="4146d-123">Select the overwrite location to reuse the same location.</span></span> <span data-ttu-id="4146d-124">或者指定一个新位置。</span><span class="sxs-lookup"><span data-stu-id="4146d-124">Or specify a new location.</span></span>  <span data-ttu-id="4146d-125">在 WCF 服务发布向导中，选择**覆盖现有位置**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4146d-125">In the WCF Service Publishing Wizard, select **Overwrite Existing Location** and click **Next**.</span></span> <span data-ttu-id="4146d-126">此步骤将覆盖该位置。</span><span class="sxs-lookup"><span data-stu-id="4146d-126">This step overwrites the location.</span></span>