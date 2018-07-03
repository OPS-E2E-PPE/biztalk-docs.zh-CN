---
title: 单一登录： 事件 10739 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08c0b5194b3c6cb2a75966a33d7215fd0b7b499
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969446"
---
# <a name="single-sign-on-event-10739"></a><span data-ttu-id="cfb42-102">单一登录： 事件 10739</span><span class="sxs-lookup"><span data-stu-id="cfb42-102">Single Sign-On: Event 10739</span></span>
## <a name="details"></a><span data-ttu-id="cfb42-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cfb42-103">Details</span></span>  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cfb42-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cfb42-104">Product Name</span></span>   |                                                                               <span data-ttu-id="cfb42-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cfb42-105">Enterprise Single Sign-On</span></span>                                                                               |
| <span data-ttu-id="cfb42-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cfb42-106">Product Version</span></span> |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    <span data-ttu-id="cfb42-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cfb42-107">Event ID</span></span>     |                                                                                         <span data-ttu-id="cfb42-108">10739</span><span class="sxs-lookup"><span data-stu-id="cfb42-108">10739</span></span>                                                                                         |
|  <span data-ttu-id="cfb42-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cfb42-109">Event Source</span></span>   |                                                                                        <span data-ttu-id="cfb42-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cfb42-110">ENTSSO</span></span>                                                                                         |
|    <span data-ttu-id="cfb42-111">组件</span><span class="sxs-lookup"><span data-stu-id="cfb42-111">Component</span></span>    |                                                                                          <span data-ttu-id="cfb42-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cfb42-112">N\A</span></span>                                                                                          |
|  <span data-ttu-id="cfb42-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cfb42-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="cfb42-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="cfb42-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span></span>                                                                        |
|  <span data-ttu-id="cfb42-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cfb42-115">Message Text</span></span>   | <span data-ttu-id="cfb42-116">更新 SSO 数据库中的 Windows 密码失败。%r</span><span class="sxs-lookup"><span data-stu-id="cfb42-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="cfb42-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cfb42-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="cfb42-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="cfb42-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="cfb42-119">Windows 帐户： %3\\%4 %r</span><span class="sxs-lookup"><span data-stu-id="cfb42-119">Windows Account: %3\\%4%r</span></span><br /><br /> <span data-ttu-id="cfb42-120">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="cfb42-120">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="cfb42-121">解释</span><span class="sxs-lookup"><span data-stu-id="cfb42-121">Explanation</span></span>  
 <span data-ttu-id="cfb42-122">此警告事件表示 SSO 更新 SSO 数据库中的 Windows 密码失败。</span><span class="sxs-lookup"><span data-stu-id="cfb42-122">This Warning event indicates that SSO failed to update the Windows password in the SSO database.</span></span> <span data-ttu-id="cfb42-123">导致该警告消息中描述的失败的原因有很多，在某些情况下，此警告可能表示配置问题，或者是在进行密码更改时删除了映射。</span><span class="sxs-lookup"><span data-stu-id="cfb42-123">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cfb42-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="cfb42-124">User Action</span></span>  
 <span data-ttu-id="cfb42-125">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cfb42-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="cfb42-126">重试更改密码。</span><span class="sxs-lookup"><span data-stu-id="cfb42-126">Retry the password change.</span></span>  

- <span data-ttu-id="cfb42-127">如果更多的尝试继续失败，则使用 UI 或命令行工具来手动更改密码。</span><span class="sxs-lookup"><span data-stu-id="cfb42-127">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="cfb42-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="cfb42-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="cfb42-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="cfb42-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
