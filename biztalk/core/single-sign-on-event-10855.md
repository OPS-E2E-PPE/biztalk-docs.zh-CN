---
title: "单一登录： 事件 10855 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89bbdb3c004dc7533be9b7f6371ec69b67bde532
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10855"></a><span data-ttu-id="93079-102">单一登录： 事件 10855</span><span class="sxs-lookup"><span data-stu-id="93079-102">Single Sign-On: Event 10855</span></span>
|||  
|-|-|  
|<span data-ttu-id="93079-103">产品名称</span><span class="sxs-lookup"><span data-stu-id="93079-103">Product Name</span></span>|<span data-ttu-id="93079-104">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="93079-104">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="93079-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="93079-105">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="93079-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="93079-106">Event ID</span></span>|<span data-ttu-id="93079-107">10855</span><span class="sxs-lookup"><span data-stu-id="93079-107">10855</span></span>|  
|<span data-ttu-id="93079-108">事件源</span><span class="sxs-lookup"><span data-stu-id="93079-108">Event Source</span></span>|<span data-ttu-id="93079-109">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="93079-109">ENTSSO</span></span>|  
|<span data-ttu-id="93079-110">组件</span><span class="sxs-lookup"><span data-stu-id="93079-110">Component</span></span>|<span data-ttu-id="93079-111">N/A</span><span class="sxs-lookup"><span data-stu-id="93079-111">N/A</span></span>|  
|<span data-ttu-id="93079-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="93079-112">Symbolic Name</span></span>|<span data-ttu-id="93079-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="93079-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span></span>|  
|<span data-ttu-id="93079-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="93079-114">Message Text</span></span>|<span data-ttu-id="93079-115">无法返回凭据，因为密码筛选器出现故障。</span><span class="sxs-lookup"><span data-stu-id="93079-115">The credentials cannot be returned because the password filter failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="93079-116">解释</span><span class="sxs-lookup"><span data-stu-id="93079-116">Explanation</span></span>  
 <span data-ttu-id="93079-117">密码筛选器无效。</span><span class="sxs-lookup"><span data-stu-id="93079-117">The password filter is not valid.</span></span> <span data-ttu-id="93079-118">最可能的原因是手动创建的该筛选器，这不是推荐的方法。</span><span class="sxs-lookup"><span data-stu-id="93079-118">The most likely cause of this is that the filter was created manually, which is not recommended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93079-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="93079-119">User Action</span></span>  
 <span data-ttu-id="93079-120">再次使用“创建筛选器”向导创建密码筛选器。</span><span class="sxs-lookup"><span data-stu-id="93079-120">Create the password filter again using the Create Filter wizard.</span></span>