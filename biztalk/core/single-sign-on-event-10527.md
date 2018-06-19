---
title: 单一登录： 事件 10527 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf1785361ad343b3da4c7dc07b6a73a362fa14d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270197"
---
# <a name="single-sign-on-event-10527"></a><span data-ttu-id="39869-102">单一登录： 事件 10527</span><span class="sxs-lookup"><span data-stu-id="39869-102">Single Sign-On: Event 10527</span></span>
## <a name="details"></a><span data-ttu-id="39869-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="39869-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39869-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="39869-104">Product Name</span></span>|<span data-ttu-id="39869-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="39869-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="39869-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="39869-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="39869-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="39869-107">Event ID</span></span>|<span data-ttu-id="39869-108">10527</span><span class="sxs-lookup"><span data-stu-id="39869-108">10527</span></span>|  
|<span data-ttu-id="39869-109">事件源</span><span class="sxs-lookup"><span data-stu-id="39869-109">Event Source</span></span>|<span data-ttu-id="39869-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="39869-110">ENTSSO</span></span>|  
|<span data-ttu-id="39869-111">组件</span><span class="sxs-lookup"><span data-stu-id="39869-111">Component</span></span>|<span data-ttu-id="39869-112">0</span><span class="sxs-lookup"><span data-stu-id="39869-112">0</span></span>|  
|<span data-ttu-id="39869-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="39869-113">Symbolic Name</span></span>|<span data-ttu-id="39869-114">SSO_ERROR_GET_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="39869-114">SSO_ERROR_GET_SECRET_FAILED</span></span>|  
|<span data-ttu-id="39869-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="39869-115">Message Text</span></span>|<span data-ttu-id="39869-116">获取主密钥的请求失败。%r</span><span class="sxs-lookup"><span data-stu-id="39869-116">A request to get a master secret failed.%r</span></span><br /><br /> <span data-ttu-id="39869-117">机密数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="39869-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="39869-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="39869-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="39869-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="39869-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="39869-120">跟踪 ID: %4 %r</span><span class="sxs-lookup"><span data-stu-id="39869-120">Tracking ID: %4%r</span></span><br /><br /> <span data-ttu-id="39869-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="39869-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="39869-122">解释</span><span class="sxs-lookup"><span data-stu-id="39869-122">Explanation</span></span>  
 <span data-ttu-id="39869-123">此错误事件表示获取主密钥的请求失败。</span><span class="sxs-lookup"><span data-stu-id="39869-123">This Error event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="39869-124">在这些情况下应用程序事件日志中应会出现相关的消息。</span><span class="sxs-lookup"><span data-stu-id="39869-124">In these cases there should be related messages in the Application event log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39869-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="39869-125">User Action</span></span>  
 <span data-ttu-id="39869-126">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="39869-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="39869-127">请检查关联的事件或错误的应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="39869-127">Check the Application event log for associated events or errors.</span></span>  
  
 <span data-ttu-id="39869-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="39869-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="39869-129">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="39869-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="39869-130">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="39869-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)