---
title: 单一登录： 事件 10849 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdfb1cea-e445-4318-9891-b6b70a266ca9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3ef1e5454c80f5aba963426c04950c33a2f773a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276933"
---
# <a name="single-sign-on-event-10849"></a><span data-ttu-id="3f0c0-102">单一登录： 事件 10849</span><span class="sxs-lookup"><span data-stu-id="3f0c0-102">Single Sign-On: Event 10849</span></span>
## <a name="details"></a><span data-ttu-id="3f0c0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3f0c0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f0c0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3f0c0-104">Product Name</span></span>|<span data-ttu-id="3f0c0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3f0c0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3f0c0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3f0c0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3f0c0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3f0c0-107">Event ID</span></span>|<span data-ttu-id="3f0c0-108">10849</span><span class="sxs-lookup"><span data-stu-id="3f0c0-108">10849</span></span>|  
|<span data-ttu-id="3f0c0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3f0c0-109">Event Source</span></span>|<span data-ttu-id="3f0c0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3f0c0-110">ENTSSO</span></span>|  
|<span data-ttu-id="3f0c0-111">组件</span><span class="sxs-lookup"><span data-stu-id="3f0c0-111">Component</span></span>|<span data-ttu-id="3f0c0-112">N/A</span><span class="sxs-lookup"><span data-stu-id="3f0c0-112">N/A</span></span>|  
|<span data-ttu-id="3f0c0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3f0c0-113">Symbolic Name</span></span>|<span data-ttu-id="3f0c0-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="3f0c0-114">ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE</span></span>|  
|<span data-ttu-id="3f0c0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3f0c0-115">Message Text</span></span>|<span data-ttu-id="3f0c0-116">无法创建指定了“直接密码同步”标志的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f0c0-116">An application cannot be created with the ‘direct password sync’ flag specified.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f0c0-117">解释</span><span class="sxs-lookup"><span data-stu-id="3f0c0-117">Explanation</span></span>  
 <span data-ttu-id="3f0c0-118">无法创建指定了“直接密码同步”标志的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f0c0-118">An application cannot be created with the ‘direct password sync’ flag specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f0c0-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="3f0c0-119">User Action</span></span>  
 <span data-ttu-id="3f0c0-120">创建应用程序不直接密码同步标志。</span><span class="sxs-lookup"><span data-stu-id="3f0c0-120">Create the application without the direct password sync flag.</span></span> <span data-ttu-id="3f0c0-121">然后添加并创建字段，启用该应用程序，再指定直接密码同步标志。</span><span class="sxs-lookup"><span data-stu-id="3f0c0-121">Then add and create the fields, enable the application, and specify the direct password sync flag.</span></span>