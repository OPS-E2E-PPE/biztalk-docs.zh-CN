---
title: 传统的单一登录应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ffc09f49e6fecc1d6773a3b5ea8e89f8d98ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313327"
---
# <a name="traditional-single-sign-on-applications"></a><span data-ttu-id="104d6-102">传统的单一登录应用程序</span><span class="sxs-lookup"><span data-stu-id="104d6-102">Traditional Single Sign-On Applications</span></span>
<span data-ttu-id="104d6-103">单一登录 (SSO) 编程体系结构包含一个映射组件的应用程序和用户、 要查找指定用途凭据的查找组件和管理组件来执行管理任务之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="104d6-103">The Single Sign-On (SSO) programming architecture contains a mapping component to map between applications and users, a lookup component to look up credentials for a specified use, and an administration component to perform administrative tasks.</span></span> <span data-ttu-id="104d6-104">此外，SSO 还包含一个票证接口，以便你的应用程序可颁发和兑换票证。</span><span class="sxs-lookup"><span data-stu-id="104d6-104">In addition, SSO also contains a ticketing interface so that your application can issue and redeem tickets.</span></span>  
  
## <a name="mapping"></a><span data-ttu-id="104d6-105">映射</span><span class="sxs-lookup"><span data-stu-id="104d6-105">Mapping</span></span>  
 <span data-ttu-id="104d6-106">映射是链接具有指定的应用程序的指定的用户的过程。</span><span class="sxs-lookup"><span data-stu-id="104d6-106">Mapping is the process of linking a specified user with a specified application.</span></span> <span data-ttu-id="104d6-107">您可以关联应用程序和使用用户之间的映射`ISSOMapping`， `ISSOMapper`，和`ISSOMapper2`。</span><span class="sxs-lookup"><span data-stu-id="104d6-107">You can map between affiliate applications and users who are using `ISSOMapping`, `ISSOMapper`, and `ISSOMapper2`.</span></span> <span data-ttu-id="104d6-108">使用`ISSOMapping`，可以创建、 删除、 启用和禁用映射。</span><span class="sxs-lookup"><span data-stu-id="104d6-108">With `ISSOMapping`, you can create, delete, enable, and disable mappings.</span></span> <span data-ttu-id="104d6-109">与`ISSOMapper`，和`ISSOMapper2`，可以获取并设置为当前用户的映射数据。</span><span class="sxs-lookup"><span data-stu-id="104d6-109">With `ISSOMapper`, and `ISSOMapper2`, you can get and set mapping data for the current user.</span></span>  
  
## <a name="lookup"></a><span data-ttu-id="104d6-110">查找</span><span class="sxs-lookup"><span data-stu-id="104d6-110">Lookup</span></span>  
 <span data-ttu-id="104d6-111">单一登录编程接口的核心是查找指定的用户凭据的功能。</span><span class="sxs-lookup"><span data-stu-id="104d6-111">The core of the Single Sign-On programming interface is the ability to look up credentials for specified users.</span></span> <span data-ttu-id="104d6-112">您可以查看使用的凭据`ISSOLookup1`，和`ISSOLookup2`。</span><span class="sxs-lookup"><span data-stu-id="104d6-112">You can look up credentials using `ISSOLookup1`, and `ISSOLookup2`.</span></span> <span data-ttu-id="104d6-113">`ISSOLookup1`使用户能够检索其自己的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="104d6-113">`ISSOLookup1`, enables the user to retrieve their own external credentials.</span></span> <span data-ttu-id="104d6-114">与此相反，`ISSOLookup2`还使您能够查找本地关联应用程序的远程用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="104d6-114">In contrast, `ISSOLookup2` also enables you to look up the credentials of a remote user for a local affiliate application.</span></span> <span data-ttu-id="104d6-115">前者是必需的传统上单一登录的应用程序，而后者时，可以编写一个主机启动的单一登录应用程序。</span><span class="sxs-lookup"><span data-stu-id="104d6-115">The former is necessary for a traditional Single Sign-On application, whereas the latter is useful when you are writing a host-initiated Single Sign-On application.</span></span>  
  
## <a name="administration"></a><span data-ttu-id="104d6-116">管理</span><span class="sxs-lookup"><span data-stu-id="104d6-116">Administration</span></span>  
 <span data-ttu-id="104d6-117">你可以执行许多管理功能以编程方式通过`ISSOAdmin`， `ISSOAdmin2`，和`ISSOConfigStore`。</span><span class="sxs-lookup"><span data-stu-id="104d6-117">You can perform many of the administrative capabilities programmatically through `ISSOAdmin`, `ISSOAdmin2`, and `ISSOConfigStore`.</span></span> <span data-ttu-id="104d6-118">此类任务包括配置单一登录以及创建和描述为实现单一登录的应用程序。</span><span class="sxs-lookup"><span data-stu-id="104d6-118">Such tasks include configuring Single Sign-On and creating and describing an application to Single Sign-On.</span></span> <span data-ttu-id="104d6-119">此外可以创建和修改使用的 SSO 数据库`ISSOConfigDB`， `ISSOConfigOM`，和`ISSOConfigSS`。</span><span class="sxs-lookup"><span data-stu-id="104d6-119">You also can create and modify SSO databases using `ISSOConfigDB`, `ISSOConfigOM`, and `ISSOConfigSS`.</span></span> <span data-ttu-id="104d6-120">最后，您可以管理使用的密码同步功能`ISSOPSAdmin`。</span><span class="sxs-lookup"><span data-stu-id="104d6-120">Finally, you can administer the password sync features using `ISSOPSAdmin`.</span></span>  
  
## <a name="communication-and-ticketing"></a><span data-ttu-id="104d6-121">通信和票证</span><span class="sxs-lookup"><span data-stu-id="104d6-121">Communication and Ticketing</span></span>  
 <span data-ttu-id="104d6-122">你的应用程序将很可能需要发出消息，以便用户可以与远程应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="104d6-122">Your application will most likely issue messages so that your user can communicate with a remote application.</span></span> <span data-ttu-id="104d6-123">若要更安全地与远程应用程序通信，必须颁发和兑换单一登录票证。</span><span class="sxs-lookup"><span data-stu-id="104d6-123">To communicate with a remote application more securely, you must issue and redeem a Single Sign-On ticket.</span></span> <span data-ttu-id="104d6-124">您还可以颁发和兑换票证以编程方式。</span><span class="sxs-lookup"><span data-stu-id="104d6-124">You can also issue and redeem tickets programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104d6-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="104d6-125">See Also</span></span>  
 [<span data-ttu-id="104d6-126">单一登录应用程序</span><span class="sxs-lookup"><span data-stu-id="104d6-126">Single Sign-On Applications</span></span>](../core/single-sign-on-applications.md)