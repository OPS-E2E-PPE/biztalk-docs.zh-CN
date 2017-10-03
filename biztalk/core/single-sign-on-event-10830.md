---
title: "单一登录： 事件 10830 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd149be1-0a4f-4d39-9b0e-35202dc140cb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5944fe4e0af6c5e0484fd344d08ef839901e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10830"></a><span data-ttu-id="398f1-102">单一登录： 事件 10830</span><span class="sxs-lookup"><span data-stu-id="398f1-102">Single Sign-On: Event 10830</span></span>
## <a name="details"></a><span data-ttu-id="398f1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="398f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="398f1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="398f1-104">Product Name</span></span>|<span data-ttu-id="398f1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="398f1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="398f1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="398f1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="398f1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="398f1-107">Event ID</span></span>|<span data-ttu-id="398f1-108">10830</span><span class="sxs-lookup"><span data-stu-id="398f1-108">10830</span></span>|  
|<span data-ttu-id="398f1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="398f1-109">Event Source</span></span>|<span data-ttu-id="398f1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="398f1-110">ENTSSO</span></span>|  
|<span data-ttu-id="398f1-111">组件</span><span class="sxs-lookup"><span data-stu-id="398f1-111">Component</span></span>|<span data-ttu-id="398f1-112">N/A</span><span class="sxs-lookup"><span data-stu-id="398f1-112">N/A</span></span>|  
|<span data-ttu-id="398f1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="398f1-113">Symbolic Name</span></span>|<span data-ttu-id="398f1-114">ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="398f1-114">ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER</span></span>|  
|<span data-ttu-id="398f1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="398f1-115">Message Text</span></span>|<span data-ttu-id="398f1-116">指定的适配器必须位于组适配器所在的计算机上。</span><span class="sxs-lookup"><span data-stu-id="398f1-116">The specified adapter must be on the same computer as the group adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="398f1-117">解释</span><span class="sxs-lookup"><span data-stu-id="398f1-117">Explanation</span></span>  
 <span data-ttu-id="398f1-118">必须使用位于组适配器所在的相同计算机名称配置组适配器中的每个适配器。</span><span class="sxs-lookup"><span data-stu-id="398f1-118">Each adapter in a group adapter must be configured with the same computer name as the group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="398f1-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="398f1-119">User Action</span></span>  
 <span data-ttu-id="398f1-120">有关详细信息，请参阅[密码同步](../core/password-synchronization2.md)</span><span class="sxs-lookup"><span data-stu-id="398f1-120">For more information, see [Password Synchronization](../core/password-synchronization2.md)</span></span>  
  
 <span data-ttu-id="398f1-121">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="398f1-121">.</span></span>