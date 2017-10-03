---
title: "单一登录： 事件 10818 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be2c40fa5da46f5045b55c815be9f6f8048cda67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10818"></a><span data-ttu-id="252e2-102">单一登录： 事件 10818</span><span class="sxs-lookup"><span data-stu-id="252e2-102">Single Sign-On: Event 10818</span></span>
## <a name="details"></a><span data-ttu-id="252e2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="252e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="252e2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="252e2-104">Product Name</span></span>|<span data-ttu-id="252e2-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="252e2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="252e2-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="252e2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="252e2-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="252e2-107">Event ID</span></span>|<span data-ttu-id="252e2-108">10818</span><span class="sxs-lookup"><span data-stu-id="252e2-108">10818</span></span>|  
|<span data-ttu-id="252e2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="252e2-109">Event Source</span></span>|<span data-ttu-id="252e2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="252e2-110">ENTSSO</span></span>|  
|<span data-ttu-id="252e2-111">组件</span><span class="sxs-lookup"><span data-stu-id="252e2-111">Component</span></span>|<span data-ttu-id="252e2-112">N/A</span><span class="sxs-lookup"><span data-stu-id="252e2-112">N/A</span></span>|  
|<span data-ttu-id="252e2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="252e2-113">Symbolic Name</span></span>|<span data-ttu-id="252e2-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span><span class="sxs-lookup"><span data-stu-id="252e2-114">ENTSSO_E_AMBIGUOUS_SYNC_FIELDS</span></span>|  
|<span data-ttu-id="252e2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="252e2-115">Message Text</span></span>|<span data-ttu-id="252e2-116">应用程序必须具有两个字段或者只有一个字段必须标记为同步。</span><span class="sxs-lookup"><span data-stu-id="252e2-116">The application must have two fields or only one field must be marked for sync.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="252e2-117">解释</span><span class="sxs-lookup"><span data-stu-id="252e2-117">Explanation</span></span>  
 <span data-ttu-id="252e2-118">如果存在两个以上字段，则必须只对一个字段标记为密码同步。</span><span class="sxs-lookup"><span data-stu-id="252e2-118">If there are more than two fields, then one and only one must be marked for password sync.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="252e2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="252e2-119">User Action</span></span>  
 <span data-ttu-id="252e2-120">若要更正这种情况下，必须删除该应用程序，并重新创建它，以便它遵循这些准则。</span><span class="sxs-lookup"><span data-stu-id="252e2-120">To remedy this situation, you must delete the application and recreate it so that it follows these guidelines.</span></span>