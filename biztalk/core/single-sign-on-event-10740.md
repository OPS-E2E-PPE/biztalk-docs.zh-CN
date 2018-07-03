---
title: 单一登录： 事件 10740 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9bf7c2cdaae3cffe280035f007cd1b49d2c70c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970054"
---
# <a name="single-sign-on-event-10740"></a><span data-ttu-id="52329-102">单一登录： 事件 10740</span><span class="sxs-lookup"><span data-stu-id="52329-102">Single Sign-On: Event 10740</span></span>
## <a name="details"></a><span data-ttu-id="52329-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="52329-103">Details</span></span>  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="52329-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="52329-104">Product Name</span></span>   |                                                                 <span data-ttu-id="52329-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="52329-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="52329-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="52329-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="52329-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="52329-107">Event ID</span></span>     |                                                                           <span data-ttu-id="52329-108">10740</span><span class="sxs-lookup"><span data-stu-id="52329-108">10740</span></span>                                                                            |
|  <span data-ttu-id="52329-109">事件源</span><span class="sxs-lookup"><span data-stu-id="52329-109">Event Source</span></span>   |                                                                           <span data-ttu-id="52329-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="52329-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="52329-111">组件</span><span class="sxs-lookup"><span data-stu-id="52329-111">Component</span></span>    |                                                                            <span data-ttu-id="52329-112">N\A</span><span class="sxs-lookup"><span data-stu-id="52329-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="52329-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="52329-113">Symbolic Name</span></span>  |                                                               <span data-ttu-id="52329-114">SSO_WARN_INVALID_WINDOWS_USER</span><span class="sxs-lookup"><span data-stu-id="52329-114">SSO_WARN_INVALID_WINDOWS_USER</span></span>                                                                |
|  <span data-ttu-id="52329-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="52329-115">Message Text</span></span>   | <span data-ttu-id="52329-116">此 Windows 帐户不能用于应用程序更新。%r</span><span class="sxs-lookup"><span data-stu-id="52329-116">The Windows Account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="52329-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="52329-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="52329-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="52329-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="52329-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="52329-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="52329-120">解释</span><span class="sxs-lookup"><span data-stu-id="52329-120">Explanation</span></span>  
 <span data-ttu-id="52329-121">此警告事件表明，该 Windows 帐户（在事件消息中指定）不能用于应用程序更新。</span><span class="sxs-lookup"><span data-stu-id="52329-121">This Warning event indicates that the Windows Account (specified in the event message) is not valid for application update.</span></span> <span data-ttu-id="52329-122">为主机组应用程序更改 Windows 帐户时可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="52329-122">This can occur when changing the Windows account for a Host Group application.</span></span> <span data-ttu-id="52329-123">主机组应用程序用于从外部系统到 Windows 系统的单一登录。</span><span class="sxs-lookup"><span data-stu-id="52329-123">Host Group applications are used for single sign-on from external systems to Windows systems.</span></span> <span data-ttu-id="52329-124">这些应用程序可将一组外部用户映射到单个 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="52329-124">They can map a set of external users to a single Windows account.</span></span> <span data-ttu-id="52329-125">该应用程序的“应用程序用户”字段中定义了所映射到的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="52329-125">The Windows account they are mapped to is defined in the Application Users field of the application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="52329-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="52329-126">User Action</span></span>  
 <span data-ttu-id="52329-127">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52329-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="52329-128">检查您所使用的 Windows 帐户是否有效。</span><span class="sxs-lookup"><span data-stu-id="52329-128">Check that the Windows account your are using is valid.</span></span>  

- <span data-ttu-id="52329-129">重新创建具有正确 Windows 帐户属性的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="52329-129">Recreate the Windows account with the correct Windows account properties.</span></span>  

  <span data-ttu-id="52329-130">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="52329-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="52329-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="52329-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
