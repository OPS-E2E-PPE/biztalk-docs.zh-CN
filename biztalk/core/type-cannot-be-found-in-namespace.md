---
title: "命名空间中找不到类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 515dd9b6b73b43bee22ffc7b67745bb45adcaf6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="type-cannot-be-found-in-namespace"></a><span data-ttu-id="7e661-102">命名空间中找不到类型</span><span class="sxs-lookup"><span data-stu-id="7e661-102">Type cannot be found in namespace</span></span>
## <a name="details"></a><span data-ttu-id="7e661-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7e661-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e661-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7e661-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7e661-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7e661-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7e661-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7e661-106">Event ID</span></span>|<span data-ttu-id="7e661-107">0</span><span class="sxs-lookup"><span data-stu-id="7e661-107">0</span></span>|  
|<span data-ttu-id="7e661-108">事件源</span><span class="sxs-lookup"><span data-stu-id="7e661-108">Event Source</span></span>|<span data-ttu-id="7e661-109">0</span><span class="sxs-lookup"><span data-stu-id="7e661-109">0</span></span>|  
|<span data-ttu-id="7e661-110">组件</span><span class="sxs-lookup"><span data-stu-id="7e661-110">Component</span></span>|<span data-ttu-id="7e661-111">0</span><span class="sxs-lookup"><span data-stu-id="7e661-111">0</span></span>|  
|<span data-ttu-id="7e661-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="7e661-112">Symbolic Name</span></span>|<span data-ttu-id="7e661-113">0</span><span class="sxs-lookup"><span data-stu-id="7e661-113">0</span></span>|  
|<span data-ttu-id="7e661-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="7e661-114">Message Text</span></span>|<span data-ttu-id="7e661-115">错误： 无法在命名空间"{1}"中找到类型"{0}"</span><span class="sxs-lookup"><span data-stu-id="7e661-115">Error: Type "{0}" cannot be found in namespace "{1}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e661-116">解释</span><span class="sxs-lookup"><span data-stu-id="7e661-116">Explanation</span></span>  
 <span data-ttu-id="7e661-117">此错误表示所创建的项目参考的是无法在指定的命名空间中找到的类型。</span><span class="sxs-lookup"><span data-stu-id="7e661-117">This error indicates artifacts that are created are referencing types which cannot be found in the namespace specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e661-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7e661-118">User Action</span></span>  
 <span data-ttu-id="7e661-119">添加包含无法找到的类型的引用，然后再次运行向导（如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="7e661-119">Add a reference that contain the type that is not found, and run the wizard again (if you own the WCF service that you are trying to consume).</span></span> <span data-ttu-id="7e661-120">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="7e661-120">Otherwise, contact the service provider.</span></span>