---
title: 单一登录：Event 10776 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 155919fa-f88d-4257-b09c-8765c83d896f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fd90909f05417ef8780f220e71079c09f5cca01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394205"
---
# <a name="single-sign-on-event-10776"></a><span data-ttu-id="1cc5d-102">单一登录：事件 10776</span><span class="sxs-lookup"><span data-stu-id="1cc5d-102">Single Sign-On: Event 10776</span></span>
## <a name="details"></a><span data-ttu-id="1cc5d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1cc5d-103">Details</span></span>  
  
|                 |                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1cc5d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1cc5d-104">Product Name</span></span>   |                                                               <span data-ttu-id="1cc5d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1cc5d-105">Enterprise Single Sign-On</span></span>                                                               |
| <span data-ttu-id="1cc5d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1cc5d-106">Product Version</span></span> |                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    <span data-ttu-id="1cc5d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1cc5d-107">Event ID</span></span>     |                                                                         <span data-ttu-id="1cc5d-108">10776</span><span class="sxs-lookup"><span data-stu-id="1cc5d-108">10776</span></span>                                                                         |
|  <span data-ttu-id="1cc5d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1cc5d-109">Event Source</span></span>   |                                                                        <span data-ttu-id="1cc5d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1cc5d-110">ENTSSO</span></span>                                                                         |
|    <span data-ttu-id="1cc5d-111">组件</span><span class="sxs-lookup"><span data-stu-id="1cc5d-111">Component</span></span>    |                                                                          <span data-ttu-id="1cc5d-112">不可用</span><span class="sxs-lookup"><span data-stu-id="1cc5d-112">N/A</span></span>                                                                          |
|  <span data-ttu-id="1cc5d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1cc5d-113">Symbolic Name</span></span>  |                                                            <span data-ttu-id="1cc5d-114">ENTSSO_E_INVALID_ACCOUNT_FORMAT</span><span class="sxs-lookup"><span data-stu-id="1cc5d-114">ENTSSO_E_INVALID_ACCOUNT_FORMAT</span></span>                                                            |
|  <span data-ttu-id="1cc5d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1cc5d-115">Message Text</span></span>   | <span data-ttu-id="1cc5d-116">帐户名称的格式无效。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-116">The format of the account name is not valid.</span></span> <span data-ttu-id="1cc5d-117">域帐户必须包含域名称。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-117">Domain accounts must include the domain name.</span></span> <span data-ttu-id="1cc5d-118">本地帐户必须包括域名或计算机名。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-118">Local accounts must not include a domain or computer name.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1cc5d-119">解释</span><span class="sxs-lookup"><span data-stu-id="1cc5d-119">Explanation</span></span>  
 <span data-ttu-id="1cc5d-120">帐户名称的格式无效。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-120">The format of the account name is not valid.</span></span> <span data-ttu-id="1cc5d-121">域帐户必须包含域名称。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-121">Domain accounts must include the domain name.</span></span> <span data-ttu-id="1cc5d-122">本地帐户必须包括域名或计算机名。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-122">Local accounts must not include a domain or computer name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cc5d-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="1cc5d-123">User Action</span></span>  
 <span data-ttu-id="1cc5d-124">指定一个不同的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="1cc5d-124">Specify a different account name.</span></span>