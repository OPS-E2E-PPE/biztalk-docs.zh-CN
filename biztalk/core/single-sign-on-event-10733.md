---
title: 单一登录： 事件 10733 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1387d7c853bba91bea429470d9a615e065a6e8dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271525"
---
# <a name="single-sign-on-event-10733"></a><span data-ttu-id="f3033-102">单一登录： 事件 10733</span><span class="sxs-lookup"><span data-stu-id="f3033-102">Single Sign-On: Event 10733</span></span>
## <a name="details"></a><span data-ttu-id="f3033-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f3033-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3033-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f3033-104">Product Name</span></span>|<span data-ttu-id="f3033-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f3033-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f3033-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f3033-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f3033-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f3033-107">Event ID</span></span>|<span data-ttu-id="f3033-108">10733</span><span class="sxs-lookup"><span data-stu-id="f3033-108">10733</span></span>|  
|<span data-ttu-id="f3033-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f3033-109">Event Source</span></span>|<span data-ttu-id="f3033-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f3033-110">ENTSSO</span></span>|  
|<span data-ttu-id="f3033-111">组件</span><span class="sxs-lookup"><span data-stu-id="f3033-111">Component</span></span>|<span data-ttu-id="f3033-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f3033-112">N\A</span></span>|  
|<span data-ttu-id="f3033-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f3033-113">Symbolic Name</span></span>|<span data-ttu-id="f3033-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="f3033-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span></span>|  
|<span data-ttu-id="f3033-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f3033-115">Message Text</span></span>|<span data-ttu-id="f3033-116">更新 SSO 数据库中的 Windows 密码失败。%r</span><span class="sxs-lookup"><span data-stu-id="f3033-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="f3033-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f3033-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f3033-118">Windows 帐户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="f3033-118">Windows Account: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="f3033-119">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="f3033-119">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3033-120">解释</span><span class="sxs-lookup"><span data-stu-id="f3033-120">Explanation</span></span>  
 <span data-ttu-id="f3033-121">此警告事件表示密码同步更新在 SSO 数据库中指定的 Windows 帐户密码失败。</span><span class="sxs-lookup"><span data-stu-id="f3033-121">This Warning event indicates that Password Sync failed to update the specified Windows account password in the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3033-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="f3033-122">User Action</span></span>  
 <span data-ttu-id="f3033-123">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="f3033-123">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="f3033-124">检查相关错误的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="f3033-124">Check the system and application event logs for associated errors.</span></span>  
  
-   <span data-ttu-id="f3033-125">验证指定帐户的密码是否为有效的 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="f3033-125">Verify the password for the specified account is a valid Windows password.</span></span>  
  
 <span data-ttu-id="f3033-126">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f3033-126">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="f3033-127">密码同步</span><span class="sxs-lookup"><span data-stu-id="f3033-127">Password Synchronization</span></span>](../core/password-synchronization2.md)