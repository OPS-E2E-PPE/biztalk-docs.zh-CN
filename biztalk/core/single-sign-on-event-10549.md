---
title: 单一登录： 事件 10549 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a59feecdcf5daeef7013dd99eca1e778d49278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270461"
---
# <a name="single-sign-on-event-10549"></a><span data-ttu-id="ef36b-102">单一登录： 事件 10549</span><span class="sxs-lookup"><span data-stu-id="ef36b-102">Single Sign-On: Event 10549</span></span>
## <a name="details"></a><span data-ttu-id="ef36b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef36b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef36b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ef36b-104">Product Name</span></span>|<span data-ttu-id="ef36b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ef36b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ef36b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ef36b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ef36b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ef36b-107">Event ID</span></span>|<span data-ttu-id="ef36b-108">10549</span><span class="sxs-lookup"><span data-stu-id="ef36b-108">10549</span></span>|  
|<span data-ttu-id="ef36b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ef36b-109">Event Source</span></span>|<span data-ttu-id="ef36b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ef36b-110">ENTSSO</span></span>|  
|<span data-ttu-id="ef36b-111">组件</span><span class="sxs-lookup"><span data-stu-id="ef36b-111">Component</span></span>|<span data-ttu-id="ef36b-112">CO</span><span class="sxs-lookup"><span data-stu-id="ef36b-112">CO</span></span>|  
|<span data-ttu-id="ef36b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ef36b-113">Symbolic Name</span></span>|<span data-ttu-id="ef36b-114">SSO_ERROR_CREATE_DATABASE_FAILED</span><span class="sxs-lookup"><span data-stu-id="ef36b-114">SSO_ERROR_CREATE_DATABASE_FAILED</span></span>|  
|<span data-ttu-id="ef36b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ef36b-115">Message Text</span></span>|<span data-ttu-id="ef36b-116">创建并初始化该 SSO 数据库失败。%r</span><span class="sxs-lookup"><span data-stu-id="ef36b-116">Creation and initialization of the SSO database failed.%r</span></span><br /><br /> <span data-ttu-id="ef36b-117">SQL Server 名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ef36b-117">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="ef36b-118">SSO 数据库名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ef36b-118">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="ef36b-119">客户端用户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ef36b-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="ef36b-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="ef36b-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef36b-121">解释</span><span class="sxs-lookup"><span data-stu-id="ef36b-121">Explanation</span></span>  
 <span data-ttu-id="ef36b-122">此错误表示创建和初始化 SSO 数据库的失败。</span><span class="sxs-lookup"><span data-stu-id="ef36b-122">This Error indicates that creation and initialization of the SSO database failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef36b-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="ef36b-123">User Action</span></span>  
 <span data-ttu-id="ef36b-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ef36b-124">To resolve this error do the following:</span></span>  
  
-   <span data-ttu-id="ef36b-125">查看系统和应用程序事件日志了解相关消息。</span><span class="sxs-lookup"><span data-stu-id="ef36b-125">Check the system and application event logs for associated messages.</span></span>  
  
-   <span data-ttu-id="ef36b-126">再次运行 Setup。</span><span class="sxs-lookup"><span data-stu-id="ef36b-126">Run Setup again.</span></span>  
  
 <span data-ttu-id="ef36b-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="ef36b-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ef36b-128">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="ef36b-128">Installing SSO</span></span>](../core/installing-sso.md)