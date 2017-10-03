---
title: "单一登录： 事件 10821 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2200011e-3e4f-4fe4-b01f-f3b86cdc96db
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f212a77f85330d256f1415ec13f3ec267e4be7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10821"></a><span data-ttu-id="2559f-102">单一登录： 事件 10821</span><span class="sxs-lookup"><span data-stu-id="2559f-102">Single Sign-On: Event 10821</span></span>
## <a name="details"></a><span data-ttu-id="2559f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2559f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2559f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2559f-104">Product Name</span></span>|<span data-ttu-id="2559f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2559f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2559f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2559f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2559f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2559f-107">Event ID</span></span>|<span data-ttu-id="2559f-108">10821</span><span class="sxs-lookup"><span data-stu-id="2559f-108">10821</span></span>|  
|<span data-ttu-id="2559f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2559f-109">Event Source</span></span>|<span data-ttu-id="2559f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2559f-110">ENTSSO</span></span>|  
|<span data-ttu-id="2559f-111">组件</span><span class="sxs-lookup"><span data-stu-id="2559f-111">Component</span></span>|<span data-ttu-id="2559f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="2559f-112">N/A</span></span>|  
|<span data-ttu-id="2559f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2559f-113">Symbolic Name</span></span>|<span data-ttu-id="2559f-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="2559f-114">ENTSSO_E_ADAPTER_ASSIGNED_TO_GROUP_ADAPTER</span></span>|  
|<span data-ttu-id="2559f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2559f-115">Message Text</span></span>|<span data-ttu-id="2559f-116">无法删除适配器，因为它当前已分配给一个组适配器。</span><span class="sxs-lookup"><span data-stu-id="2559f-116">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2559f-117">解释</span><span class="sxs-lookup"><span data-stu-id="2559f-117">Explanation</span></span>  
 <span data-ttu-id="2559f-118">无法删除适配器，因为它当前已分配给一个组适配器。</span><span class="sxs-lookup"><span data-stu-id="2559f-118">The adapter cannot be deleted because it is currently assigned to a group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2559f-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="2559f-119">User Action</span></span>  
 <span data-ttu-id="2559f-120">取消分配该适配器，然后删除它。</span><span class="sxs-lookup"><span data-stu-id="2559f-120">Unassign the adapter and then delete it.</span></span>