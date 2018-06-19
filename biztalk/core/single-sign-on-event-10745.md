---
title: 单一登录： 事件 10745 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe734562b9d8b3564a08f3f5196d53996bf40ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270821"
---
# <a name="single-sign-on-event-10745"></a><span data-ttu-id="2f6a9-102">单一登录： 事件 10745</span><span class="sxs-lookup"><span data-stu-id="2f6a9-102">Single Sign-On: Event 10745</span></span>
## <a name="details"></a><span data-ttu-id="2f6a9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2f6a9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f6a9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2f6a9-104">Product Name</span></span>|<span data-ttu-id="2f6a9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2f6a9-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2f6a9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2f6a9-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2f6a9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2f6a9-107">Event ID</span></span>|<span data-ttu-id="2f6a9-108">10745</span><span class="sxs-lookup"><span data-stu-id="2f6a9-108">10745</span></span>|  
|<span data-ttu-id="2f6a9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2f6a9-109">Event Source</span></span>|<span data-ttu-id="2f6a9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2f6a9-110">ENTSSO</span></span>|  
|<span data-ttu-id="2f6a9-111">组件</span><span class="sxs-lookup"><span data-stu-id="2f6a9-111">Component</span></span>|<span data-ttu-id="2f6a9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="2f6a9-112">N\A</span></span>|  
|<span data-ttu-id="2f6a9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2f6a9-113">Symbolic Name</span></span>|<span data-ttu-id="2f6a9-114">SSO_ERROR_ADAPTER_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="2f6a9-114">SSO_ERROR_ADAPTER_OFFLINE</span></span>|  
|<span data-ttu-id="2f6a9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2f6a9-115">Message Text</span></span>|<span data-ttu-id="2f6a9-116">适配器处于脱机状态。%r</span><span class="sxs-lookup"><span data-stu-id="2f6a9-116">The adapter is offline.%r</span></span><br /><br /> <span data-ttu-id="2f6a9-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2f6a9-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="2f6a9-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="2f6a9-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="2f6a9-119">错误消息: %3 %r</span><span class="sxs-lookup"><span data-stu-id="2f6a9-119">Error Message: %3%r</span></span><br /><br /> <span data-ttu-id="2f6a9-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="2f6a9-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2f6a9-121">解释</span><span class="sxs-lookup"><span data-stu-id="2f6a9-121">Explanation</span></span>  
 <span data-ttu-id="2f6a9-122">此错误事件表示指定的适配器处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="2f6a9-122">This Error event indicates that the specified adapter is offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f6a9-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="2f6a9-123">User Action</span></span>  
 <span data-ttu-id="2f6a9-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="2f6a9-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="2f6a9-125">检查相关错误的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="2f6a9-125">Check the system and application event logs for associated errors.</span></span>  
  
-   <span data-ttu-id="2f6a9-126">检查外部适配器是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="2f6a9-126">Check the external adapter for errors.</span></span>  
  
 <span data-ttu-id="2f6a9-127">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="2f6a9-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="2f6a9-128">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="2f6a9-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)