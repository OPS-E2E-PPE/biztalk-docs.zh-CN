---
title: 单一登录： 事件 10568 |Microsoft Docs
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
ms.openlocfilehash: 8c94c99580b63c5dc6eede29b595435daa256115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010246"
---
# <a name="single-sign-on-event-10568"></a><span data-ttu-id="12b3a-102">单一登录： 事件 10568</span><span class="sxs-lookup"><span data-stu-id="12b3a-102">Single Sign-On: Event 10568</span></span>
## <a name="details"></a><span data-ttu-id="12b3a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="12b3a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="12b3a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="12b3a-104">Product Name</span></span>   |                                                                                                  <span data-ttu-id="12b3a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="12b3a-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="12b3a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="12b3a-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    <span data-ttu-id="12b3a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="12b3a-107">Event ID</span></span>     |                                                                                                            <span data-ttu-id="12b3a-108">10568</span><span class="sxs-lookup"><span data-stu-id="12b3a-108">10568</span></span>                                                                                                            |
|  <span data-ttu-id="12b3a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="12b3a-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="12b3a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="12b3a-110">ENTSSO</span></span>                                                                                                            |
|    <span data-ttu-id="12b3a-111">组件</span><span class="sxs-lookup"><span data-stu-id="12b3a-111">Component</span></span>    |                                                                                                             <span data-ttu-id="12b3a-112">N/A</span><span class="sxs-lookup"><span data-stu-id="12b3a-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="12b3a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="12b3a-113">Symbolic Name</span></span>  |                                                                                              <span data-ttu-id="12b3a-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="12b3a-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span></span>                                                                                               |
|  <span data-ttu-id="12b3a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="12b3a-115">Message Text</span></span>   | <span data-ttu-id="12b3a-116">应用程序管理员帐户无法用于应用程序更新。%r</span><span class="sxs-lookup"><span data-stu-id="12b3a-116">The Application Administrators account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="12b3a-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="12b3a-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="12b3a-118">应用程序管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="12b3a-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="12b3a-119">无效帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="12b3a-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="12b3a-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="12b3a-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="12b3a-121">解释</span><span class="sxs-lookup"><span data-stu-id="12b3a-121">Explanation</span></span>  
 <span data-ttu-id="12b3a-122">您尝试更新的应用程序管理员帐户无效或不存在。</span><span class="sxs-lookup"><span data-stu-id="12b3a-122">You have attempted to update an Application Administrators account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12b3a-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="12b3a-123">User Action</span></span>  
 <span data-ttu-id="12b3a-124">检查帐户的名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="12b3a-124">Check that the name of the account is correct.</span></span>