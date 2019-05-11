---
title: 单一登录：事件 10569 |Microsoft Docs
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
ms.openlocfilehash: 21e3c6e7650e61af9811cd58542a7a4d2b6204af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398755"
---
# <a name="single-sign-on-event-10569"></a><span data-ttu-id="6cf1c-102">单一登录：事件 10569</span><span class="sxs-lookup"><span data-stu-id="6cf1c-102">Single Sign-On: Event 10569</span></span>
## <a name="details"></a><span data-ttu-id="6cf1c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6cf1c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6cf1c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6cf1c-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="6cf1c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6cf1c-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="6cf1c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6cf1c-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="6cf1c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6cf1c-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="6cf1c-108">10569</span><span class="sxs-lookup"><span data-stu-id="6cf1c-108">10569</span></span>                                                                                                  |
|  <span data-ttu-id="6cf1c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6cf1c-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="6cf1c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6cf1c-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="6cf1c-111">组件</span><span class="sxs-lookup"><span data-stu-id="6cf1c-111">Component</span></span>    |                                                                                                  <span data-ttu-id="6cf1c-112">不可用</span><span class="sxs-lookup"><span data-stu-id="6cf1c-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="6cf1c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6cf1c-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="6cf1c-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="6cf1c-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span></span>                                                                                     |
|  <span data-ttu-id="6cf1c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6cf1c-115">Message Text</span></span>   | <span data-ttu-id="6cf1c-116">应用程序 Administrator.%r 不能更改应用程序管理员帐户</span><span class="sxs-lookup"><span data-stu-id="6cf1c-116">The Application Administrators account cannot be changed by an Application Administrator.%r</span></span><br /><br /> <span data-ttu-id="6cf1c-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6cf1c-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="6cf1c-118">应用程序管理员: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6cf1c-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="6cf1c-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="6cf1c-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6cf1c-120">解释</span><span class="sxs-lookup"><span data-stu-id="6cf1c-120">Explanation</span></span>  
 <span data-ttu-id="6cf1c-121">不能由应用程序管理员更改应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="6cf1c-121">The Application Administrators account cannot be changed by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6cf1c-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="6cf1c-122">User Action</span></span>  
 <span data-ttu-id="6cf1c-123">您必须是一个 SSO 关联应用程序管理员或更高版本来更改应用程序管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="6cf1c-123">You must be an SSO Affiliate Application Administrator or higher to change the Application Administratos account.</span></span>