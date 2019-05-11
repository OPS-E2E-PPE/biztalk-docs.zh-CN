---
title: 单一登录：Event 10557 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5cd5be8005a1ce13c1ad5f13c580e6e72353b9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398839"
---
# <a name="single-sign-on-event-10557"></a><span data-ttu-id="7bf1b-102">单一登录：事件 10557</span><span class="sxs-lookup"><span data-stu-id="7bf1b-102">Single Sign-On: Event 10557</span></span>
## <a name="details"></a><span data-ttu-id="7bf1b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7bf1b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7bf1b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7bf1b-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="7bf1b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7bf1b-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="7bf1b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7bf1b-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="7bf1b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7bf1b-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="7bf1b-108">10557</span><span class="sxs-lookup"><span data-stu-id="7bf1b-108">10557</span></span>                                                                                                   |
|  <span data-ttu-id="7bf1b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7bf1b-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="7bf1b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7bf1b-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="7bf1b-111">组件</span><span class="sxs-lookup"><span data-stu-id="7bf1b-111">Component</span></span>    |                                                                                                   <span data-ttu-id="7bf1b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="7bf1b-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="7bf1b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7bf1b-113">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="7bf1b-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span><span class="sxs-lookup"><span data-stu-id="7bf1b-114">SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS</span></span>                                                                                   |
|  <span data-ttu-id="7bf1b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7bf1b-115">Message Text</span></span>   | <span data-ttu-id="7bf1b-116">不允许应用程序用户控制的组 applications.%r 映射</span><span class="sxs-lookup"><span data-stu-id="7bf1b-116">Application Users are not allowed to control mappings for Group applications.%r</span></span><br /><br /> <span data-ttu-id="7bf1b-117">域名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7bf1b-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="7bf1b-118">用户名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7bf1b-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="7bf1b-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7bf1b-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="7bf1b-120">客户端用户： %4</span><span class="sxs-lookup"><span data-stu-id="7bf1b-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7bf1b-121">解释</span><span class="sxs-lookup"><span data-stu-id="7bf1b-121">Explanation</span></span>  
 <span data-ttu-id="7bf1b-122">应用程序用户没有足够的特权创建或控制组应用程序的映射。</span><span class="sxs-lookup"><span data-stu-id="7bf1b-122">An Application User does not have sufficient privileges to create or control mappings for Group applications.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7bf1b-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="7bf1b-123">User Action</span></span>  
 <span data-ttu-id="7bf1b-124">必须由应用程序管理员执行此活动。</span><span class="sxs-lookup"><span data-stu-id="7bf1b-124">This activity must be performed by an Application Administrator.</span></span>