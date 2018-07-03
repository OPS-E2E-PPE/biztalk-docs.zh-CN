---
title: 单一登录： 事件 10574 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f2a5aa-3a19-4d7c-9257-89f1567a3c2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3700f565dafb9003a3cc05d9e52c7559904f88
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976950"
---
# <a name="single-sign-on-event-10574"></a><span data-ttu-id="ed348-102">单一登录： 事件 10574</span><span class="sxs-lookup"><span data-stu-id="ed348-102">Single Sign-On: Event 10574</span></span>
## <a name="details"></a><span data-ttu-id="ed348-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ed348-103">Details</span></span>  
  
|                 |                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ed348-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ed348-104">Product Name</span></span>   |                                                                        <span data-ttu-id="ed348-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ed348-105">Enterprise Single Sign-On</span></span>                                                                         |
| <span data-ttu-id="ed348-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ed348-106">Product Version</span></span> |                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                        |
|    <span data-ttu-id="ed348-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ed348-107">Event ID</span></span>     |                                                                                  <span data-ttu-id="ed348-108">10574</span><span class="sxs-lookup"><span data-stu-id="ed348-108">10574</span></span>                                                                                   |
|  <span data-ttu-id="ed348-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ed348-109">Event Source</span></span>   |                                                                                  <span data-ttu-id="ed348-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ed348-110">ENTSSO</span></span>                                                                                  |
|    <span data-ttu-id="ed348-111">组件</span><span class="sxs-lookup"><span data-stu-id="ed348-111">Component</span></span>    |                                                                                   <span data-ttu-id="ed348-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ed348-112">N/A</span></span>                                                                                    |
|  <span data-ttu-id="ed348-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ed348-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="ed348-114">SSO_WARN_INVALID_SSO_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="ed348-114">SSO_WARN_INVALID_SSO_ADMIN_GROUP</span></span>                                                                     |
|  <span data-ttu-id="ed348-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ed348-115">Message Text</span></span>   | <span data-ttu-id="ed348-116">SSO 管理员帐户不能用于全局信息更新。%r</span><span class="sxs-lookup"><span data-stu-id="ed348-116">The SSO Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="ed348-117">SSO Administrators: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ed348-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="ed348-118">无效帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ed348-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="ed348-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="ed348-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ed348-120">解释</span><span class="sxs-lookup"><span data-stu-id="ed348-120">Explanation</span></span>  
 <span data-ttu-id="ed348-121">SSO 管理员帐户不能用于全局信息更新。</span><span class="sxs-lookup"><span data-stu-id="ed348-121">The SSO Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ed348-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ed348-122">User Action</span></span>  
 <span data-ttu-id="ed348-123">此警告消息包含有关 SSO 管理员帐户和无效帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="ed348-123">The warning message contains information regarding the SSO Administrators account and the invalid accounts.</span></span> <span data-ttu-id="ed348-124">查看此信息，进行任何必要的更正，然后重试更新。</span><span class="sxs-lookup"><span data-stu-id="ed348-124">Review this information, make any necessary corrections, and try the update again.</span></span>