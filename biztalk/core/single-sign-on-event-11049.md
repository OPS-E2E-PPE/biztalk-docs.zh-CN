---
title: "单一登录： 事件 11049 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ac6095950e02e7e73ab287b180bc22d88b4191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11049"></a><span data-ttu-id="f0323-102">单一登录： 事件 11049</span><span class="sxs-lookup"><span data-stu-id="f0323-102">Single Sign-On: Event 11049</span></span>
## <a name="details"></a><span data-ttu-id="f0323-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f0323-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0323-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f0323-104">Product Name</span></span>|<span data-ttu-id="f0323-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f0323-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f0323-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f0323-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f0323-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f0323-107">Event ID</span></span>|<span data-ttu-id="f0323-108">11049</span><span class="sxs-lookup"><span data-stu-id="f0323-108">11049</span></span>|  
|<span data-ttu-id="f0323-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f0323-109">Event Source</span></span>|<span data-ttu-id="f0323-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f0323-110">ENTSSO</span></span>|  
|<span data-ttu-id="f0323-111">组件</span><span class="sxs-lookup"><span data-stu-id="f0323-111">Component</span></span>|<span data-ttu-id="f0323-112">N/A</span><span class="sxs-lookup"><span data-stu-id="f0323-112">N/A</span></span>|  
|<span data-ttu-id="f0323-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f0323-113">Symbolic Name</span></span>|<span data-ttu-id="f0323-114">SSO_ERROR_DTC_FAILED</span><span class="sxs-lookup"><span data-stu-id="f0323-114">SSO_ERROR_DTC_FAILED</span></span>|  
|<span data-ttu-id="f0323-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f0323-115">Message Text</span></span>|<span data-ttu-id="f0323-116">无法获取 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="f0323-116">Could not get MSDTC.</span></span> <span data-ttu-id="f0323-117">SSO 需要具备 MSDTC 才能进行正确操作。</span><span class="sxs-lookup"><span data-stu-id="f0323-117">SSO requires MSDTC for correct operation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0323-118">解释</span><span class="sxs-lookup"><span data-stu-id="f0323-118">Explanation</span></span>  
 <span data-ttu-id="f0323-119">ENTSSO 系统无法连接到 Microsoft 分布式事务处理协调器 (MSDTC)。</span><span class="sxs-lookup"><span data-stu-id="f0323-119">The ENTSSO system could not connect to the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0323-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="f0323-120">User Action</span></span>  
 <span data-ttu-id="f0323-121">检查 MSDTC 当前是否可操作。</span><span class="sxs-lookup"><span data-stu-id="f0323-121">Check to see if MSDTC is currently operational.</span></span>  
  
 <span data-ttu-id="f0323-122">有关 MSDTC 问题的帮助，请参阅[问题疑难解答与 MSDTC](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="f0323-122">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>