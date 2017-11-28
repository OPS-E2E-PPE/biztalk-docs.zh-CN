---
title: "单一登录： 事件 10757 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5887694e8fd307c0738fc7596c52354925bfbc7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10757"></a><span data-ttu-id="d8150-102">单一登录： 事件 10757</span><span class="sxs-lookup"><span data-stu-id="d8150-102">Single Sign-On: Event 10757</span></span>
## <a name="details"></a><span data-ttu-id="d8150-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d8150-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8150-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d8150-104">Product Name</span></span>|<span data-ttu-id="d8150-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d8150-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d8150-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d8150-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d8150-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d8150-107">Event ID</span></span>|<span data-ttu-id="d8150-108">10757</span><span class="sxs-lookup"><span data-stu-id="d8150-108">10757</span></span>|  
|<span data-ttu-id="d8150-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d8150-109">Event Source</span></span>|<span data-ttu-id="d8150-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d8150-110">ENTSSO</span></span>|  
|<span data-ttu-id="d8150-111">组件</span><span class="sxs-lookup"><span data-stu-id="d8150-111">Component</span></span>|<span data-ttu-id="d8150-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d8150-112">N/A</span></span>|  
|<span data-ttu-id="d8150-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d8150-113">Symbolic Name</span></span>|<span data-ttu-id="d8150-114">ENTSSO_E_NO_MAPPING</span><span class="sxs-lookup"><span data-stu-id="d8150-114">ENTSSO_E_NO_MAPPING</span></span>|  
|<span data-ttu-id="d8150-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d8150-115">Message Text</span></span>|<span data-ttu-id="d8150-116">映射不存在。</span><span class="sxs-lookup"><span data-stu-id="d8150-116">The mapping does not exist.</span></span> <span data-ttu-id="d8150-117">对于配置存储应用程序，尚未设置配置信息。</span><span class="sxs-lookup"><span data-stu-id="d8150-117">For Config Store applications, the config info has not been set.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8150-118">解释</span><span class="sxs-lookup"><span data-stu-id="d8150-118">Explanation</span></span>  
 <span data-ttu-id="d8150-119">如果这是个人或组类型的应用程序，则不存在映射。</span><span class="sxs-lookup"><span data-stu-id="d8150-119">If this is an Individual or Group type application, then the mapping does not exist.</span></span>  
  
 <span data-ttu-id="d8150-120">如果这是配置存储应用程序，则尚未设置配置数据。</span><span class="sxs-lookup"><span data-stu-id="d8150-120">If this is a Config Store application, then the configuration data has not been set.</span></span> <span data-ttu-id="d8150-121">当已重新初始化 SSO 数据库，但尚未重新初始化 BizTalk 管理数据库时，会发生此情况，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d8150-121">This can occur when the SSO database has been reinitialized but the BizTalk Management database has not, or vice versa.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8150-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="d8150-122">User Action</span></span>  
 <span data-ttu-id="d8150-123">如果这是个人或组类型的应用程序，则创建所需的映射。</span><span class="sxs-lookup"><span data-stu-id="d8150-123">If this is an Individual or Group type application, create the desired mapping.</span></span> <span data-ttu-id="d8150-124">有关详细信息，请参阅[如何创建用户映射](../core/how-to-create-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="d8150-124">For more information, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>