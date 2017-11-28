---
title: "单一登录： 事件 10529 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f33c0e475f9b54b5fc0a5d5415736d9717ccdf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10529"></a><span data-ttu-id="18116-102">单一登录： 事件 10529</span><span class="sxs-lookup"><span data-stu-id="18116-102">Single Sign-On: Event 10529</span></span>
## <a name="details"></a><span data-ttu-id="18116-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="18116-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="18116-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="18116-104">Product Name</span></span>|<span data-ttu-id="18116-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="18116-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="18116-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="18116-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="18116-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="18116-107">Event ID</span></span>|<span data-ttu-id="18116-108">10529</span><span class="sxs-lookup"><span data-stu-id="18116-108">10529</span></span>|  
|<span data-ttu-id="18116-109">事件源</span><span class="sxs-lookup"><span data-stu-id="18116-109">Event Source</span></span>|<span data-ttu-id="18116-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="18116-110">ENTSSO</span></span>|  
|<span data-ttu-id="18116-111">组件</span><span class="sxs-lookup"><span data-stu-id="18116-111">Component</span></span>|<span data-ttu-id="18116-112">N\A</span><span class="sxs-lookup"><span data-stu-id="18116-112">N\A</span></span>|  
|<span data-ttu-id="18116-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="18116-113">Symbolic Name</span></span>|<span data-ttu-id="18116-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="18116-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>|  
|<span data-ttu-id="18116-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="18116-115">Message Text</span></span>|<span data-ttu-id="18116-116">从主密钥服务器获取最新密钥。%r</span><span class="sxs-lookup"><span data-stu-id="18116-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="18116-117">机密的服务器名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="18116-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="18116-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="18116-118">MSID: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="18116-119">解释</span><span class="sxs-lookup"><span data-stu-id="18116-119">Explanation</span></span>  
 <span data-ttu-id="18116-120">此信息事件表明 SSO 具有主密钥服务器请求的主密钥。</span><span class="sxs-lookup"><span data-stu-id="18116-120">This Information event indicates that SSO has the requested master secret from the master secret server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="18116-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="18116-121">User Action</span></span>  
  
-   <span data-ttu-id="18116-122">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="18116-122">No user action is necessary.</span></span>  
  
 <span data-ttu-id="18116-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="18116-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="18116-124">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="18116-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="18116-125">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="18116-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)