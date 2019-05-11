---
title: 单一登录：Event 10595 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6aecfef61ece56075c4eb0c47ba7852380d4c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397843"
---
# <a name="single-sign-on-event-10595"></a><span data-ttu-id="81469-102">单一登录：事件 10595</span><span class="sxs-lookup"><span data-stu-id="81469-102">Single Sign-On: Event 10595</span></span>
## <a name="details"></a><span data-ttu-id="81469-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="81469-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="81469-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="81469-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="81469-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="81469-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="81469-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="81469-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="81469-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="81469-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="81469-108">10595</span><span class="sxs-lookup"><span data-stu-id="81469-108">10595</span></span>                                                                                                        |
|  <span data-ttu-id="81469-109">事件源</span><span class="sxs-lookup"><span data-stu-id="81469-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="81469-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="81469-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="81469-111">组件</span><span class="sxs-lookup"><span data-stu-id="81469-111">Component</span></span>    |                                                                                                        <span data-ttu-id="81469-112">不可用</span><span class="sxs-lookup"><span data-stu-id="81469-112">N/A</span></span>                                                                                                         |
|  <span data-ttu-id="81469-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="81469-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="81469-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span><span class="sxs-lookup"><span data-stu-id="81469-114">SSO_WARN_APP_INCOMPLETE_FIELDS</span></span>                                                                                           |
|  <span data-ttu-id="81469-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="81469-115">Message Text</span></span>   | <span data-ttu-id="81469-116">无法启用应用程序，因为的字段不全 application.%r</span><span class="sxs-lookup"><span data-stu-id="81469-116">The application cannot be enabled because the fields are incomplete for this application.%r</span></span><br /><br /> <span data-ttu-id="81469-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="81469-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="81469-118">定义的字段数: %2 %r</span><span class="sxs-lookup"><span data-stu-id="81469-118">Number of Fields Defined: %2%r</span></span><br /><br /> <span data-ttu-id="81469-119">创建的字段数： %3</span><span class="sxs-lookup"><span data-stu-id="81469-119">Number of Fields Created: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="81469-120">解释</span><span class="sxs-lookup"><span data-stu-id="81469-120">Explanation</span></span>  
 <span data-ttu-id="81469-121">在创建时应用程序在 API 级别，您指定的字段 (即用户 Id 和密码) 会定义应用程序的数目。</span><span class="sxs-lookup"><span data-stu-id="81469-121">When creating an application at the API level, you specified the number of fields (i.e. UserID, Password) the application would define.</span></span> <span data-ttu-id="81469-122">此外必须创建每个已定义的字段。</span><span class="sxs-lookup"><span data-stu-id="81469-122">Each field that has been defined must also be created.</span></span> <span data-ttu-id="81469-123">此警告消息列出了应用程序名称、 字段定义，数和创建的字段数。</span><span class="sxs-lookup"><span data-stu-id="81469-123">This warning message lists the application name, number of fields defined, and number of fields created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81469-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="81469-124">User Action</span></span>  
 <span data-ttu-id="81469-125">确定哪些字段已定义但未创建，然后返回并创建它们。</span><span class="sxs-lookup"><span data-stu-id="81469-125">Determine which fields were defined but not created, and then go back and create them.</span></span>