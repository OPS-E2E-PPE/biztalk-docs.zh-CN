---
title: 单一登录： 事件 10850 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0430d5d7ea3ff2a0fabf9c9698acffe15b644f24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011358"
---
# <a name="single-sign-on-event-10850"></a><span data-ttu-id="02acb-102">单一登录： 事件 10850</span><span class="sxs-lookup"><span data-stu-id="02acb-102">Single Sign-On: Event 10850</span></span>
## <a name="details"></a><span data-ttu-id="02acb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="02acb-103">Details</span></span>  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  <span data-ttu-id="02acb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="02acb-104">Product Name</span></span>   |                      <span data-ttu-id="02acb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="02acb-105">Enterprise Single Sign-On</span></span>                      |
| <span data-ttu-id="02acb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="02acb-106">Product Version</span></span> |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="02acb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="02acb-107">Event ID</span></span>     |                                <span data-ttu-id="02acb-108">10850</span><span class="sxs-lookup"><span data-stu-id="02acb-108">10850</span></span>                                |
|  <span data-ttu-id="02acb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="02acb-109">Event Source</span></span>   |                               <span data-ttu-id="02acb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="02acb-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="02acb-111">组件</span><span class="sxs-lookup"><span data-stu-id="02acb-111">Component</span></span>    |                                 <span data-ttu-id="02acb-112">N/A</span><span class="sxs-lookup"><span data-stu-id="02acb-112">N/A</span></span>                                 |
|  <span data-ttu-id="02acb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="02acb-113">Symbolic Name</span></span>  |                 <span data-ttu-id="02acb-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="02acb-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span></span>                 |
|  <span data-ttu-id="02acb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="02acb-115">Message Text</span></span>   | <span data-ttu-id="02acb-116">不能创建已指定“已启用”标志的应用程序。</span><span class="sxs-lookup"><span data-stu-id="02acb-116">An application cannot be created with the 'enabled' flag specified.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="02acb-117">解释</span><span class="sxs-lookup"><span data-stu-id="02acb-117">Explanation</span></span>  
 <span data-ttu-id="02acb-118">启用应用程序前，需要先创建该应用程序，并为其每个字段（如，用户 ID 和密码）输入字段信息。</span><span class="sxs-lookup"><span data-stu-id="02acb-118">Before enabling an application, it is necessary to both create the application and enter the field information for each of its fields (i.e. UserID and Password).</span></span> <span data-ttu-id="02acb-119">不能创建已设置“已启用”字段的应用程序。</span><span class="sxs-lookup"><span data-stu-id="02acb-119">It is not possible to create an application with the “enabled” field already set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="02acb-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="02acb-120">User Action</span></span>  
 <span data-ttu-id="02acb-121">使用创建应用程序 API 或新建关联应用程序向导再次创建该应用程序。</span><span class="sxs-lookup"><span data-stu-id="02acb-121">Create the application again (using either the Create Application API or the Create New Affiliate Application Wizard).</span></span> <span data-ttu-id="02acb-122">应用程序创建完成并填充字段后，启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="02acb-122">When the application is complete and the fields populated, enable the application.</span></span>