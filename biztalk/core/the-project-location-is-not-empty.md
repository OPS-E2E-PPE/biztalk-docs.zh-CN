---
title: 项目位置不为空 |Microsoft Docs
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
ms.openlocfilehash: 6fd44cc0d9bfefb67b96558808e6b98a46c8afc2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394090"
---
# <a name="the-project-location-is-not-empty"></a><span data-ttu-id="b45f0-102">项目位置不为空</span><span class="sxs-lookup"><span data-stu-id="b45f0-102">The project location is not empty</span></span>
## <a name="details"></a><span data-ttu-id="b45f0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b45f0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b45f0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b45f0-104">Product Name</span></span>   |                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                 |
| <span data-ttu-id="b45f0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b45f0-105">Product Version</span></span> |                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                             |
|    <span data-ttu-id="b45f0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b45f0-106">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="b45f0-107">0</span><span class="sxs-lookup"><span data-stu-id="b45f0-107">0</span></span>                                                                                                                          |
|  <span data-ttu-id="b45f0-108">事件源</span><span class="sxs-lookup"><span data-stu-id="b45f0-108">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="b45f0-109">0</span><span class="sxs-lookup"><span data-stu-id="b45f0-109">0</span></span>                                                                                                                          |
|    <span data-ttu-id="b45f0-110">组件</span><span class="sxs-lookup"><span data-stu-id="b45f0-110">Component</span></span>    |                                                                                                                         <span data-ttu-id="b45f0-111">0</span><span class="sxs-lookup"><span data-stu-id="b45f0-111">0</span></span>                                                                                                                          |
|  <span data-ttu-id="b45f0-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="b45f0-112">Symbolic Name</span></span>  |                                                                                                                         <span data-ttu-id="b45f0-113">0</span><span class="sxs-lookup"><span data-stu-id="b45f0-113">0</span></span>                                                                                                                          |
|  <span data-ttu-id="b45f0-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="b45f0-114">Message Text</span></span>   | <span data-ttu-id="b45f0-115">项目位置"{0}"不为空。</span><span class="sxs-lookup"><span data-stu-id="b45f0-115">The project location "{0}" is not empty.</span></span> <span data-ttu-id="b45f0-116">需要以下项之一：1.</span><span class="sxs-lookup"><span data-stu-id="b45f0-116">You need to do one of the following: 1.</span></span> <span data-ttu-id="b45f0-117">选择新的项目中，2 的不同位置。</span><span class="sxs-lookup"><span data-stu-id="b45f0-117">Choose a different location for the new project, 2.</span></span> <span data-ttu-id="b45f0-118">指定覆盖以重用现有位置或 3。</span><span class="sxs-lookup"><span data-stu-id="b45f0-118">Specify overwrite to reuse the existing location, or 3.</span></span> <span data-ttu-id="b45f0-119">手动删除项目位置的内容。</span><span class="sxs-lookup"><span data-stu-id="b45f0-119">Manually delete the contents of the project location.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b45f0-120">解释</span><span class="sxs-lookup"><span data-stu-id="b45f0-120">Explanation</span></span>  
 <span data-ttu-id="b45f0-121">此错误表示虚拟服务正在尝试发布的目录不为空。</span><span class="sxs-lookup"><span data-stu-id="b45f0-121">This error indicates the virtual directory where the service is trying to be published is not empty.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b45f0-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="b45f0-122">User Action</span></span>  
 <span data-ttu-id="b45f0-123">选择覆盖位置以重复使用相同的位置。</span><span class="sxs-lookup"><span data-stu-id="b45f0-123">Select the overwrite location to reuse the same location.</span></span> <span data-ttu-id="b45f0-124">或指定新位置。</span><span class="sxs-lookup"><span data-stu-id="b45f0-124">Or specify a new location.</span></span>  <span data-ttu-id="b45f0-125">在 WCF 服务发布向导中，选择**覆盖现有位置**然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b45f0-125">In the WCF Service Publishing Wizard, select **Overwrite Existing Location** and click **Next**.</span></span> <span data-ttu-id="b45f0-126">此步骤将覆盖该位置。</span><span class="sxs-lookup"><span data-stu-id="b45f0-126">This step overwrites the location.</span></span>