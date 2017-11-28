---
title: "单一登录： 事件 10806 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd3f432a408cffcbd1ccd27508550fd0888c5213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="613c1-102">单一登录： 事件 10806</span><span class="sxs-lookup"><span data-stu-id="613c1-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="613c1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="613c1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="613c1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="613c1-104">Product Name</span></span>|<span data-ttu-id="613c1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="613c1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="613c1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="613c1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="613c1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="613c1-107">Event ID</span></span>|<span data-ttu-id="613c1-108">10806</span><span class="sxs-lookup"><span data-stu-id="613c1-108">10806</span></span>|  
|<span data-ttu-id="613c1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="613c1-109">Event Source</span></span>|<span data-ttu-id="613c1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="613c1-110">ENTSSO</span></span>|  
|<span data-ttu-id="613c1-111">组件</span><span class="sxs-lookup"><span data-stu-id="613c1-111">Component</span></span>|<span data-ttu-id="613c1-112">N/A</span><span class="sxs-lookup"><span data-stu-id="613c1-112">N/A</span></span>|  
|<span data-ttu-id="613c1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="613c1-113">Symbolic Name</span></span>|<span data-ttu-id="613c1-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="613c1-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>|  
|<span data-ttu-id="613c1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="613c1-115">Message Text</span></span>|<span data-ttu-id="613c1-116">无法删除该应用程序，因为它当前已分配给某个适配器。</span><span class="sxs-lookup"><span data-stu-id="613c1-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="613c1-117">解释</span><span class="sxs-lookup"><span data-stu-id="613c1-117">Explanation</span></span>  
 <span data-ttu-id="613c1-118">应用程序被分配到适配器后无法删除。</span><span class="sxs-lookup"><span data-stu-id="613c1-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="613c1-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="613c1-119">User Action</span></span>  
 <span data-ttu-id="613c1-120">取消将应用程序分配到适合器，然后再将其删除。</span><span class="sxs-lookup"><span data-stu-id="613c1-120">Unassign the application from the adapter, and then delete it.</span></span>