---
title: 单一登录： 事件 10569 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25665947921bb316a4d931228016eaf917b4a685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987198"
---
# <a name="single-sign-on-event-10569"></a><span data-ttu-id="afce6-102">单一登录： 事件 10569</span><span class="sxs-lookup"><span data-stu-id="afce6-102">Single Sign-On: Event 10569</span></span>
## <a name="details"></a><span data-ttu-id="afce6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="afce6-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="afce6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="afce6-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="afce6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="afce6-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="afce6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="afce6-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="afce6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="afce6-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="afce6-108">10569</span><span class="sxs-lookup"><span data-stu-id="afce6-108">10569</span></span>                                                                                                  |
|  <span data-ttu-id="afce6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="afce6-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="afce6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="afce6-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="afce6-111">组件</span><span class="sxs-lookup"><span data-stu-id="afce6-111">Component</span></span>    |                                                                                                  <span data-ttu-id="afce6-112">N/A</span><span class="sxs-lookup"><span data-stu-id="afce6-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="afce6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="afce6-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="afce6-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="afce6-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span></span>                                                                                     |
|  <span data-ttu-id="afce6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="afce6-115">Message Text</span></span>   | <span data-ttu-id="afce6-116">不能由应用程序管理员更改应用程序管理员帐户。%r</span><span class="sxs-lookup"><span data-stu-id="afce6-116">The Application Administrators account cannot be changed by an Application Administrator.%r</span></span><br /><br /> <span data-ttu-id="afce6-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="afce6-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="afce6-118">应用程序管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="afce6-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="afce6-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="afce6-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="afce6-120">解释</span><span class="sxs-lookup"><span data-stu-id="afce6-120">Explanation</span></span>  
 <span data-ttu-id="afce6-121">不能由应用程序管理员更改应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="afce6-121">The Application Administrators account cannot be changed by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="afce6-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="afce6-122">User Action</span></span>  
 <span data-ttu-id="afce6-123">您必须是 SSO 关联应用程序管理员或拥有更高权限，才能更改应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="afce6-123">You must be an SSO Affiliate Application Administrator or higher to change the Application Administratos account.</span></span>