---
title: 单一登录： 事件 11026 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e39b252d-2ed0-4006-aac2-4dce6504afb2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 452ccc24174a1e32a133c0ccc6c7a0b5f09c530f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013486"
---
# <a name="single-sign-on-event-11026"></a><span data-ttu-id="ed5c2-102">单一登录： 事件 11026</span><span class="sxs-lookup"><span data-stu-id="ed5c2-102">Single Sign-On: Event 11026</span></span>
## <a name="details"></a><span data-ttu-id="ed5c2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ed5c2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ed5c2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ed5c2-104">Product Name</span></span>   |                                                                                                                                <span data-ttu-id="ed5c2-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ed5c2-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="ed5c2-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ed5c2-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                |
|    <span data-ttu-id="ed5c2-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ed5c2-107">Event ID</span></span>     |                                                                                                                                          <span data-ttu-id="ed5c2-108">11026</span><span class="sxs-lookup"><span data-stu-id="ed5c2-108">11026</span></span>                                                                                                                                          |
|  <span data-ttu-id="ed5c2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ed5c2-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="ed5c2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ed5c2-110">ENTSSO</span></span>                                                                                                                                          |
|    <span data-ttu-id="ed5c2-111">组件</span><span class="sxs-lookup"><span data-stu-id="ed5c2-111">Component</span></span>    |                                                                                                                                           <span data-ttu-id="ed5c2-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ed5c2-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="ed5c2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ed5c2-113">Symbolic Name</span></span>  |                                                                                                                             <span data-ttu-id="ed5c2-114">SSO_WARN_EXISTING_GROUP_MAPPING</span><span class="sxs-lookup"><span data-stu-id="ed5c2-114">SSO_WARN_EXISTING_GROUP_MAPPING</span></span>                                                                                                                             |
|  <span data-ttu-id="ed5c2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ed5c2-115">Message Text</span></span>   | <span data-ttu-id="ed5c2-116">无法创建新的组映射，因为与现有的映射存在冲突。</span><span class="sxs-lookup"><span data-stu-id="ed5c2-116">A new group mapping could not be created because there is a conflict with an existing mapping.</span></span> <span data-ttu-id="ed5c2-117">请删除现有映射，然后重试。%r</span><span class="sxs-lookup"><span data-stu-id="ed5c2-117">Please delete the existing mapping and try again.%r</span></span><br /><br /> <span data-ttu-id="ed5c2-118">现有映射: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ed5c2-118">Existing Mapping: %1%r</span></span><br /><br /> <span data-ttu-id="ed5c2-119">新的映射: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ed5c2-119">New Mapping: %2%r</span></span><br /><br /> <span data-ttu-id="ed5c2-120">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ed5c2-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="ed5c2-121">应用程序名称： %4</span><span class="sxs-lookup"><span data-stu-id="ed5c2-121">Application Name: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ed5c2-122">解释</span><span class="sxs-lookup"><span data-stu-id="ed5c2-122">Explanation</span></span>  
 <span data-ttu-id="ed5c2-123">最可能的原因是您的系统使用的是旧版本的企业单一登录和旧的组应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed5c2-123">The most likely cause is that your system is using an old version of Enterprise Single Sign-On, and old group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed5c2-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="ed5c2-124">User Action</span></span>  
 <span data-ttu-id="ed5c2-125">删除并重新创建警告中建议的映射。</span><span class="sxs-lookup"><span data-stu-id="ed5c2-125">Delete and recreate the mapping as suggested in the warning.</span></span> <span data-ttu-id="ed5c2-126">如果该操作失败，则您可能需要升级到更新版本的企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="ed5c2-126">If this fails, you may need to upgrade to a more recent version of Enterprise Single Sign-On.</span></span>