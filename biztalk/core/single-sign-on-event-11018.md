---
title: 单一登录： 事件 11018 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83b98a1f-6390-4271-8e81-b855c4d30ec3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318928225c18a8d134d799db039058c862b034e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024515"
---
# <a name="single-sign-on-event-11018"></a><span data-ttu-id="22e40-102">单一登录： 事件 11018</span><span class="sxs-lookup"><span data-stu-id="22e40-102">Single Sign-On: Event 11018</span></span>
## <a name="details"></a><span data-ttu-id="22e40-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="22e40-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="22e40-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="22e40-104">Product Name</span></span>   |                                                                                                                              <span data-ttu-id="22e40-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="22e40-105">Enterprise Single Sign-On</span></span>                                                                                                                              |
| <span data-ttu-id="22e40-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="22e40-106">Product Version</span></span> |                                                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                              |
|    <span data-ttu-id="22e40-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="22e40-107">Event ID</span></span>     |                                                                                                                                        <span data-ttu-id="22e40-108">11018</span><span class="sxs-lookup"><span data-stu-id="22e40-108">11018</span></span>                                                                                                                                        |
|  <span data-ttu-id="22e40-109">事件源</span><span class="sxs-lookup"><span data-stu-id="22e40-109">Event Source</span></span>   |                                                                                                                                       <span data-ttu-id="22e40-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="22e40-110">ENTSSO</span></span>                                                                                                                                        |
|    <span data-ttu-id="22e40-111">组件</span><span class="sxs-lookup"><span data-stu-id="22e40-111">Component</span></span>    |                                                                                                                                         <span data-ttu-id="22e40-112">N/A</span><span class="sxs-lookup"><span data-stu-id="22e40-112">N/A</span></span>                                                                                                                                         |
|  <span data-ttu-id="22e40-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="22e40-113">Symbolic Name</span></span>  |                                                                                                                           <span data-ttu-id="22e40-114">SSO_PS_WARN_GROUP_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="22e40-114">SSO_PS_WARN_GROUP_CHECK_FAILED</span></span>                                                                                                                            |
|  <span data-ttu-id="22e40-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="22e40-115">Message Text</span></span>   | <span data-ttu-id="22e40-116">检查该映射是否为应用程序用户帐户的成员失败。</span><span class="sxs-lookup"><span data-stu-id="22e40-116">Failed to check whether the mapping was a member of the Application Users account.</span></span> <span data-ttu-id="22e40-117">将忽略此映射。%r</span><span class="sxs-lookup"><span data-stu-id="22e40-117">The mapping will be ignored.%r</span></span><br /><br /> <span data-ttu-id="22e40-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="22e40-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="22e40-119">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="22e40-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="22e40-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="22e40-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="22e40-121">应用程序用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="22e40-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="22e40-122">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="22e40-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="22e40-123">解释</span><span class="sxs-lookup"><span data-stu-id="22e40-123">Explanation</span></span>  
 <span data-ttu-id="22e40-124">Windows 发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="22e40-124">An unspecified error has occurred on the Windows side.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22e40-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="22e40-125">User Action</span></span>  
 <span data-ttu-id="22e40-126">请从警告中收集信息（跟踪 ID、Windows 帐户、应用程序名称、应用程序用户和错误代码），并与 Microsoft 产品支持服务联系。</span><span class="sxs-lookup"><span data-stu-id="22e40-126">Gather the information from the warning (Tracking ID, Windows Account, Application Name, Application Users, and Error Code) and contact Microsoft Product Support Services.</span></span>