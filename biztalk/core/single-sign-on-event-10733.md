---
title: 单一登录：Event 10733 | Microsoft Docs
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
ms.openlocfilehash: d3f67e18a9388e5f055d760d6223e2034ad6ea0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291798"
---
# <a name="single-sign-on-event-10733"></a><span data-ttu-id="a7425-102">单一登录：事件 10733</span><span class="sxs-lookup"><span data-stu-id="a7425-102">Single Sign-On: Event 10733</span></span>
## <a name="details"></a><span data-ttu-id="a7425-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a7425-103">Details</span></span>  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a7425-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a7425-104">Product Name</span></span>   |                                                                  <span data-ttu-id="a7425-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a7425-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="a7425-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a7425-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="a7425-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a7425-107">Event ID</span></span>     |                                                                            <span data-ttu-id="a7425-108">10733</span><span class="sxs-lookup"><span data-stu-id="a7425-108">10733</span></span>                                                                            |
|  <span data-ttu-id="a7425-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a7425-109">Event Source</span></span>   |                                                                           <span data-ttu-id="a7425-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a7425-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="a7425-111">组件</span><span class="sxs-lookup"><span data-stu-id="a7425-111">Component</span></span>    |                                                                             <span data-ttu-id="a7425-112">N\A</span><span class="sxs-lookup"><span data-stu-id="a7425-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="a7425-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a7425-113">Symbolic Name</span></span>  |                                                              <span data-ttu-id="a7425-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="a7425-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD</span></span>                                                               |
|  <span data-ttu-id="a7425-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a7425-115">Message Text</span></span>   | <span data-ttu-id="a7425-116">更新 SSO database.%r 中的 Windows 密码失败</span><span class="sxs-lookup"><span data-stu-id="a7425-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="a7425-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a7425-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a7425-118">Windows 帐户： %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="a7425-118">Windows Account: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="a7425-119">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="a7425-119">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="a7425-120">解释</span><span class="sxs-lookup"><span data-stu-id="a7425-120">Explanation</span></span>  
 <span data-ttu-id="a7425-121">此警告事件表示密码同步未能更新 SSO 数据库中指定的 Windows 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="a7425-121">This Warning event indicates that Password Sync failed to update the specified Windows account password in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a7425-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="a7425-122">User Action</span></span>  
 <span data-ttu-id="a7425-123">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="a7425-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="a7425-124">检查系统和应用程序事件日志中的关联错误。</span><span class="sxs-lookup"><span data-stu-id="a7425-124">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="a7425-125">验证指定帐户的密码为有效的 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="a7425-125">Verify the password for the specified account is a valid Windows password.</span></span>  

  <span data-ttu-id="a7425-126">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="a7425-126">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="a7425-127">密码同步</span><span class="sxs-lookup"><span data-stu-id="a7425-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
