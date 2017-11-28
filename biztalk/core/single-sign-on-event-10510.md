---
title: "单一登录： 事件 10510 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053f75541597e3b2e721c53714aaaf8517c3c49f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10510"></a><span data-ttu-id="6a76f-102">单一登录： 事件 10510</span><span class="sxs-lookup"><span data-stu-id="6a76f-102">Single Sign-On: Event 10510</span></span>
## <a name="details"></a><span data-ttu-id="6a76f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6a76f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a76f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6a76f-104">Product Name</span></span>|<span data-ttu-id="6a76f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6a76f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6a76f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6a76f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6a76f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6a76f-107">Event ID</span></span>|<span data-ttu-id="6a76f-108">10510</span><span class="sxs-lookup"><span data-stu-id="6a76f-108">10510</span></span>|  
|<span data-ttu-id="6a76f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6a76f-109">Event Source</span></span>|<span data-ttu-id="6a76f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6a76f-110">ENTSSO</span></span>|  
|<span data-ttu-id="6a76f-111">组件</span><span class="sxs-lookup"><span data-stu-id="6a76f-111">Component</span></span>|<span data-ttu-id="6a76f-112">N\A</span><span class="sxs-lookup"><span data-stu-id="6a76f-112">N\A</span></span>|  
|<span data-ttu-id="6a76f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6a76f-113">Symbolic Name</span></span>|<span data-ttu-id="6a76f-114">SSO_INFO_DLL_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="6a76f-114">SSO_INFO_DLL_LOAD_FAILED</span></span>|  
|<span data-ttu-id="6a76f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6a76f-115">Message Text</span></span>|<span data-ttu-id="6a76f-116">无法加载 %1。</span><span class="sxs-lookup"><span data-stu-id="6a76f-116">Failed to load %1.</span></span> <span data-ttu-id="6a76f-117">检查此文件可用。</span><span class="sxs-lookup"><span data-stu-id="6a76f-117">Check that this file is available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a76f-118">解释</span><span class="sxs-lookup"><span data-stu-id="6a76f-118">Explanation</span></span>  
 <span data-ttu-id="6a76f-119">此信息事件表示 SSO 服务加载 DLL 失败。</span><span class="sxs-lookup"><span data-stu-id="6a76f-119">This Information event indicates that the SSO service has failed to load the DLL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a76f-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="6a76f-120">User Action</span></span>  
 <span data-ttu-id="6a76f-121">若要解决此事件，请执行下列一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="6a76f-121">To resolve this event, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="6a76f-122">验证该 DLL 是否位于 SSO 安装目录中，通常为 C:\Program Files\Common Files\Enterprise Single Sign-On。</span><span class="sxs-lookup"><span data-stu-id="6a76f-122">Verify the DLL is located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="6a76f-123">您的 SSO 安装目录可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="6a76f-123">Your SSO installation directory may be different.</span></span>  
  
-   <span data-ttu-id="6a76f-124">如果一个 DLL 丢失或损坏，请尝试将其替换，然后重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="6a76f-124">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  
  
 <span data-ttu-id="6a76f-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="6a76f-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="6a76f-126">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6a76f-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)