---
title: 单一登录：事件 10850 |Microsoft Docs
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
ms.openlocfilehash: 5bd240e9176465c431ca13a5069c3d510f7c2d1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306667"
---
# <a name="single-sign-on-event-10850"></a><span data-ttu-id="c94cc-102">单一登录：事件 10850</span><span class="sxs-lookup"><span data-stu-id="c94cc-102">Single Sign-On: Event 10850</span></span>
## <a name="details"></a><span data-ttu-id="c94cc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c94cc-103">Details</span></span>  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  <span data-ttu-id="c94cc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c94cc-104">Product Name</span></span>   |                      <span data-ttu-id="c94cc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c94cc-105">Enterprise Single Sign-On</span></span>                      |
| <span data-ttu-id="c94cc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c94cc-106">Product Version</span></span> |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="c94cc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c94cc-107">Event ID</span></span>     |                                <span data-ttu-id="c94cc-108">10850</span><span class="sxs-lookup"><span data-stu-id="c94cc-108">10850</span></span>                                |
|  <span data-ttu-id="c94cc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c94cc-109">Event Source</span></span>   |                               <span data-ttu-id="c94cc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c94cc-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="c94cc-111">组件</span><span class="sxs-lookup"><span data-stu-id="c94cc-111">Component</span></span>    |                                 <span data-ttu-id="c94cc-112">不可用</span><span class="sxs-lookup"><span data-stu-id="c94cc-112">N/A</span></span>                                 |
|  <span data-ttu-id="c94cc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c94cc-113">Symbolic Name</span></span>  |                 <span data-ttu-id="c94cc-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="c94cc-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span></span>                 |
|  <span data-ttu-id="c94cc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c94cc-115">Message Text</span></span>   | <span data-ttu-id="c94cc-116">指定了已启用标志不能创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c94cc-116">An application cannot be created with the 'enabled' flag specified.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c94cc-117">解释</span><span class="sxs-lookup"><span data-stu-id="c94cc-117">Explanation</span></span>  
 <span data-ttu-id="c94cc-118">启用应用程序前, 有必要，以创建应用程序并输入其每个字段 （即用户 Id 和密码） 的字段信息。</span><span class="sxs-lookup"><span data-stu-id="c94cc-118">Before enabling an application, it is necessary to both create the application and enter the field information for each of its fields (i.e. UserID and Password).</span></span> <span data-ttu-id="c94cc-119">不能与"已启用"字段中创建的应用程序已设置。</span><span class="sxs-lookup"><span data-stu-id="c94cc-119">It is not possible to create an application with the “enabled” field already set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c94cc-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="c94cc-120">User Action</span></span>  
 <span data-ttu-id="c94cc-121">创建一次应用程序 （使用创建应用程序 API 或创建新关联应用程序向导）。</span><span class="sxs-lookup"><span data-stu-id="c94cc-121">Create the application again (using either the Create Application API or the Create New Affiliate Application Wizard).</span></span> <span data-ttu-id="c94cc-122">当应用程序已完成，字段填充，使应用程序。</span><span class="sxs-lookup"><span data-stu-id="c94cc-122">When the application is complete and the fields populated, enable the application.</span></span>