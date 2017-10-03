---
title: "单一登录： 事件 10538 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac7e027c240091e6a1a67ff53a41a00afeef7288
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10538"></a><span data-ttu-id="b4a14-102">单一登录： 事件 10538</span><span class="sxs-lookup"><span data-stu-id="b4a14-102">Single Sign-On: Event 10538</span></span>
## <a name="details"></a><span data-ttu-id="b4a14-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b4a14-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4a14-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b4a14-104">Product Name</span></span>|<span data-ttu-id="b4a14-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b4a14-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b4a14-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b4a14-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b4a14-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b4a14-107">Event ID</span></span>|<span data-ttu-id="b4a14-108">10538</span><span class="sxs-lookup"><span data-stu-id="b4a14-108">10538</span></span>|  
|<span data-ttu-id="b4a14-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b4a14-109">Event Source</span></span>|<span data-ttu-id="b4a14-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b4a14-110">ENTSSO</span></span>|  
|<span data-ttu-id="b4a14-111">组件</span><span class="sxs-lookup"><span data-stu-id="b4a14-111">Component</span></span>|<span data-ttu-id="b4a14-112">CO</span><span class="sxs-lookup"><span data-stu-id="b4a14-112">CO</span></span>|  
|<span data-ttu-id="b4a14-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b4a14-113">Symbolic Name</span></span>|<span data-ttu-id="b4a14-114">SSO_WARN_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="b4a14-114">SSO_WARN_APP_DISABLED</span></span>|  
|<span data-ttu-id="b4a14-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b4a14-115">Message Text</span></span>|<span data-ttu-id="b4a14-116">目前禁用了此应用程序。%r</span><span class="sxs-lookup"><span data-stu-id="b4a14-116">The application is currently disabled.%r</span></span><br /><br /> <span data-ttu-id="b4a14-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="b4a14-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b4a14-118">解释</span><span class="sxs-lookup"><span data-stu-id="b4a14-118">Explanation</span></span>  
 <span data-ttu-id="b4a14-119">此警告事件表示应用程序管理员已禁用了 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4a14-119">This Warning event indicates that the SSO affiliate application has been disabled by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4a14-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="b4a14-120">User Action</span></span>  
 <span data-ttu-id="b4a14-121">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="b4a14-121">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="b4a14-122">联系应用程序管理员以启用 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4a14-122">Contact your Application Administrator to enable the SSO affiliate application.</span></span> <span data-ttu-id="b4a14-123">可使用 SSO 管理工具（GUI 或命令行）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b4a14-123">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="b4a14-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="b4a14-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b4a14-125">如何启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="b4a14-125">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  
  
-   [<span data-ttu-id="b4a14-126">如何禁用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="b4a14-126">How to Disable an Affiliate Application</span></span>](../core/how-to-disable-an-affiliate-application.md)