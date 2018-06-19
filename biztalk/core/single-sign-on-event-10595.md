---
title: 单一登录： 事件 10595 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9139eb7479b0a048e2fab197863b42c47f87992a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271261"
---
# <a name="single-sign-on-event-10595"></a><span data-ttu-id="544e4-102">单一登录： 事件 10595</span><span class="sxs-lookup"><span data-stu-id="544e4-102">Single Sign-On: Event 10595</span></span>
## <a name="details"></a><span data-ttu-id="544e4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="544e4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="544e4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="544e4-104">Product Name</span></span>|<span data-ttu-id="544e4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="544e4-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="544e4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="544e4-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="544e4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="544e4-107">Event ID</span></span>|<span data-ttu-id="544e4-108">10595</span><span class="sxs-lookup"><span data-stu-id="544e4-108">10595</span></span>|  
|<span data-ttu-id="544e4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="544e4-109">Event Source</span></span>|<span data-ttu-id="544e4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="544e4-110">ENTSSO</span></span>|  
|<span data-ttu-id="544e4-111">组件</span><span class="sxs-lookup"><span data-stu-id="544e4-111">Component</span></span>|<span data-ttu-id="544e4-112">N/A</span><span class="sxs-lookup"><span data-stu-id="544e4-112">N/A</span></span>|  
|<span data-ttu-id="544e4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="544e4-113">Symbolic Name</span></span>|<span data-ttu-id="544e4-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span><span class="sxs-lookup"><span data-stu-id="544e4-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span></span>|  
|<span data-ttu-id="544e4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="544e4-115">Message Text</span></span>|<span data-ttu-id="544e4-116">由于此应用程序的字段未完成，因此无法启用该应用程序。%r</span><span class="sxs-lookup"><span data-stu-id="544e4-116">The application cannot be enabled because the fields are incomplete for this application.%r</span></span><br /><br /> <span data-ttu-id="544e4-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="544e4-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="544e4-118">定义的字段数: %2 %r</span><span class="sxs-lookup"><span data-stu-id="544e4-118">Number of Fields Defined: %2%r</span></span><br /><br /> <span data-ttu-id="544e4-119">创建的字段的数目： %3</span><span class="sxs-lookup"><span data-stu-id="544e4-119">Number of Fields Created: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="544e4-120">解释</span><span class="sxs-lookup"><span data-stu-id="544e4-120">Explanation</span></span>  
 <span data-ttu-id="544e4-121">当创建 API 级别的应用程序时，您指定了应用程序将要定义的字段数（例如：用户 ID 和密码）。</span><span class="sxs-lookup"><span data-stu-id="544e4-121">When creating an application at the API level, you specified the number of fields (i.e. UserID, Password) the application would define.</span></span> <span data-ttu-id="544e4-122">还必须创建每个已定义的字段。</span><span class="sxs-lookup"><span data-stu-id="544e4-122">Each field that has been defined must also be created.</span></span> <span data-ttu-id="544e4-123">此警告消息列出了应用程序名称、定义的字段数量，以及创建的字段数量。</span><span class="sxs-lookup"><span data-stu-id="544e4-123">This warning message lists the application name, number of fields defined, and number of fields created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="544e4-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="544e4-124">User Action</span></span>  
 <span data-ttu-id="544e4-125">确定已定义但未创建哪些字段，然后返回并创建它们。</span><span class="sxs-lookup"><span data-stu-id="544e4-125">Determine which fields were defined but not created, and then go back and create them.</span></span>