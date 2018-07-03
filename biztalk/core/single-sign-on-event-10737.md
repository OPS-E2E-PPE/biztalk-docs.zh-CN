---
title: 单一登录： 事件 10737 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd21b244e86c14aaf0f3af7418f1ca2ed8fbf067
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987678"
---
# <a name="single-sign-on-event-10737"></a><span data-ttu-id="13881-102">单一登录： 事件 10737</span><span class="sxs-lookup"><span data-stu-id="13881-102">Single Sign-On: Event 10737</span></span>
## <a name="details"></a><span data-ttu-id="13881-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="13881-103">Details</span></span>  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="13881-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="13881-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="13881-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="13881-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="13881-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="13881-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="13881-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="13881-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="13881-108">10737</span><span class="sxs-lookup"><span data-stu-id="13881-108">10737</span></span>                                                                                                          |
|  <span data-ttu-id="13881-109">事件源</span><span class="sxs-lookup"><span data-stu-id="13881-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="13881-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="13881-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="13881-111">组件</span><span class="sxs-lookup"><span data-stu-id="13881-111">Component</span></span>    |                                                                                                          <span data-ttu-id="13881-112">N\A</span><span class="sxs-lookup"><span data-stu-id="13881-112">N\A</span></span>                                                                                                           |
|  <span data-ttu-id="13881-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="13881-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="13881-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="13881-114">SSO_WARN_PS_SET_EXTERNAL_PASSWORD</span></span>                                                                                            |
|  <span data-ttu-id="13881-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="13881-115">Message Text</span></span>   | <span data-ttu-id="13881-116">更新 SSO 数据库中的外部密码失败。%r</span><span class="sxs-lookup"><span data-stu-id="13881-116">Failed to update the external password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="13881-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="13881-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="13881-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="13881-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="13881-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="13881-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="13881-120">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="13881-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="13881-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="13881-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="13881-122">解释</span><span class="sxs-lookup"><span data-stu-id="13881-122">Explanation</span></span>  
 <span data-ttu-id="13881-123">此警告事件表示 SSO 更新 SSO 数据库中的外部密码失败。</span><span class="sxs-lookup"><span data-stu-id="13881-123">This Warning event indicates that SSO failed to update the external password in the SSO database.</span></span> <span data-ttu-id="13881-124">导致该警告消息中描述的失败的原因有很多，在某些情况下，此警告可能表示配置问题，或者是在进行密码更改时删除了映射。</span><span class="sxs-lookup"><span data-stu-id="13881-124">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="13881-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="13881-125">User Action</span></span>  
 <span data-ttu-id="13881-126">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13881-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="13881-127">重试更改密码。</span><span class="sxs-lookup"><span data-stu-id="13881-127">Retry the password change.</span></span>  

- <span data-ttu-id="13881-128">如果更多的尝试继续失败，则使用 UI 或命令行工具来手动更改密码。</span><span class="sxs-lookup"><span data-stu-id="13881-128">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="13881-129">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="13881-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="13881-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="13881-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
