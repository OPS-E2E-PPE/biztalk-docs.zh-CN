---
title: 单一登录：Event 10566 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27530a47a1262cbc5baf9edede91dcee385fa91e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398780"
---
# <a name="single-sign-on-event-10566"></a><span data-ttu-id="f0e55-102">单一登录：事件 10566</span><span class="sxs-lookup"><span data-stu-id="f0e55-102">Single Sign-On: Event 10566</span></span>
## <a name="details"></a><span data-ttu-id="f0e55-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f0e55-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f0e55-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f0e55-104">Product Name</span></span>   |                                                                     <span data-ttu-id="f0e55-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f0e55-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="f0e55-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f0e55-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="f0e55-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f0e55-107">Event ID</span></span>     |                                                                               <span data-ttu-id="f0e55-108">10566</span><span class="sxs-lookup"><span data-stu-id="f0e55-108">10566</span></span>                                                                                |
|  <span data-ttu-id="f0e55-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f0e55-109">Event Source</span></span>   |                                                                               <span data-ttu-id="f0e55-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f0e55-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="f0e55-111">组件</span><span class="sxs-lookup"><span data-stu-id="f0e55-111">Component</span></span>    |                                                                                <span data-ttu-id="f0e55-112">不可用</span><span class="sxs-lookup"><span data-stu-id="f0e55-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="f0e55-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f0e55-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="f0e55-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f0e55-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span></span>                                                                  |
|  <span data-ttu-id="f0e55-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f0e55-115">Message Text</span></span>   | <span data-ttu-id="f0e55-116">无法更新一些为此应用程序指定的标志。</span><span class="sxs-lookup"><span data-stu-id="f0e55-116">You cannot update some of the specified flags for this application.</span></span> <span data-ttu-id="f0e55-117">它们将 ignored.%r</span><span class="sxs-lookup"><span data-stu-id="f0e55-117">They will be ignored.%r</span></span><br /><br /> <span data-ttu-id="f0e55-118">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f0e55-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="f0e55-119">指定标志掩码： %2</span><span class="sxs-lookup"><span data-stu-id="f0e55-119">Specified Flag Mask: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f0e55-120">解释</span><span class="sxs-lookup"><span data-stu-id="f0e55-120">Explanation</span></span>  
 <span data-ttu-id="f0e55-121">不能更改应用程序中的某些标志。</span><span class="sxs-lookup"><span data-stu-id="f0e55-121">Certain flags in an application cannot be changed.</span></span> <span data-ttu-id="f0e55-122">（例如，它不是允许将来自单独的应用程序类型更改为组。）警告文本中指定了此应用程序的标志。</span><span class="sxs-lookup"><span data-stu-id="f0e55-122">(For example, it is not allowed to change an application type from Individual to Group.) The flags for this application are specified in the warning text.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0e55-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="f0e55-123">User Action</span></span>  
 <span data-ttu-id="f0e55-124">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="f0e55-124">No user action is required.</span></span>