---
title: 单一登录： 事件 10568 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 266fd09a-c7e6-4a69-ac1c-1834097fa393
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84ca9c08d5eb6458fe3bb73ce912c577efe8937b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269701"
---
# <a name="single-sign-on-event-10568"></a><span data-ttu-id="6a7ff-102">单一登录： 事件 10568</span><span class="sxs-lookup"><span data-stu-id="6a7ff-102">Single Sign-On: Event 10568</span></span>
## <a name="details"></a><span data-ttu-id="6a7ff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6a7ff-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a7ff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6a7ff-104">Product Name</span></span>|<span data-ttu-id="6a7ff-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6a7ff-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6a7ff-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6a7ff-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6a7ff-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6a7ff-107">Event ID</span></span>|<span data-ttu-id="6a7ff-108">10568</span><span class="sxs-lookup"><span data-stu-id="6a7ff-108">10568</span></span>|  
|<span data-ttu-id="6a7ff-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6a7ff-109">Event Source</span></span>|<span data-ttu-id="6a7ff-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6a7ff-110">ENTSSO</span></span>|  
|<span data-ttu-id="6a7ff-111">组件</span><span class="sxs-lookup"><span data-stu-id="6a7ff-111">Component</span></span>|<span data-ttu-id="6a7ff-112">N/A</span><span class="sxs-lookup"><span data-stu-id="6a7ff-112">N/A</span></span>|  
|<span data-ttu-id="6a7ff-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6a7ff-113">Symbolic Name</span></span>|<span data-ttu-id="6a7ff-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="6a7ff-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="6a7ff-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6a7ff-115">Message Text</span></span>|<span data-ttu-id="6a7ff-116">应用程序管理员帐户无法用于应用程序更新。%r</span><span class="sxs-lookup"><span data-stu-id="6a7ff-116">The Application Administrators account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="6a7ff-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6a7ff-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="6a7ff-118">Application Administrators: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6a7ff-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="6a7ff-119">无效帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="6a7ff-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="6a7ff-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="6a7ff-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a7ff-121">解释</span><span class="sxs-lookup"><span data-stu-id="6a7ff-121">Explanation</span></span>  
 <span data-ttu-id="6a7ff-122">您尝试更新的应用程序管理员帐户无效或不存在。</span><span class="sxs-lookup"><span data-stu-id="6a7ff-122">You have attempted to update an Application Administrators account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6a7ff-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="6a7ff-123">User Action</span></span>  
 <span data-ttu-id="6a7ff-124">检查帐户的名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="6a7ff-124">Check that the name of the account is correct.</span></span>