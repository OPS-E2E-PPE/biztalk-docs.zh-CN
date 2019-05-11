---
title: 单一登录：Event 10575 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76cd29d85b700eadb0bce35822a2ab73493755c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295929"
---
# <a name="single-sign-on-event-10575"></a><span data-ttu-id="be3cc-102">单一登录：事件 10575</span><span class="sxs-lookup"><span data-stu-id="be3cc-102">Single Sign-On: Event 10575</span></span>
## <a name="details"></a><span data-ttu-id="be3cc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="be3cc-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="be3cc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="be3cc-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="be3cc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="be3cc-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="be3cc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="be3cc-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="be3cc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="be3cc-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="be3cc-108">10575</span><span class="sxs-lookup"><span data-stu-id="be3cc-108">10575</span></span>                                                                                               |
|  <span data-ttu-id="be3cc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="be3cc-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="be3cc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="be3cc-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="be3cc-111">组件</span><span class="sxs-lookup"><span data-stu-id="be3cc-111">Component</span></span>    |                                                                                                <span data-ttu-id="be3cc-112">不可用</span><span class="sxs-lookup"><span data-stu-id="be3cc-112">N/A</span></span>                                                                                                |
|  <span data-ttu-id="be3cc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="be3cc-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="be3cc-114">SSO_INFO_CHANGED_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="be3cc-114">SSO_INFO_CHANGED_SECRET_SERVER</span></span>                                                                                   |
|  <span data-ttu-id="be3cc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="be3cc-115">Message Text</span></span>   | <span data-ttu-id="be3cc-116">更新密钥服务器 name.%r</span><span class="sxs-lookup"><span data-stu-id="be3cc-116">Updated secret server name.%r</span></span><br /><br /> <span data-ttu-id="be3cc-117">新的服务器: %1 %r</span><span class="sxs-lookup"><span data-stu-id="be3cc-117">New Secret Server: %1%r</span></span><br /><br /> <span data-ttu-id="be3cc-118">旧密钥服务器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="be3cc-118">Old Secret Server: %2%r</span></span><br /><br /> <span data-ttu-id="be3cc-119">跟踪 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="be3cc-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="be3cc-120">客户端计算机: %4 %r</span><span class="sxs-lookup"><span data-stu-id="be3cc-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="be3cc-121">客户端用户： %5</span><span class="sxs-lookup"><span data-stu-id="be3cc-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="be3cc-122">解释</span><span class="sxs-lookup"><span data-stu-id="be3cc-122">Explanation</span></span>  
 <span data-ttu-id="be3cc-123">这是一条信息性消息，也可用于跟踪 SSO 系统中的发生的与安全相关的重要事件。</span><span class="sxs-lookup"><span data-stu-id="be3cc-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="be3cc-124">此消息表明已更新的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="be3cc-124">This message states that the secret server name has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be3cc-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="be3cc-125">User Action</span></span>  
 <span data-ttu-id="be3cc-126">不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="be3cc-126">No user action is required.</span></span>