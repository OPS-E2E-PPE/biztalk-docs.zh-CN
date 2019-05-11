---
title: 单一登录：Event 10739 | Microsoft Docs
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
ms.openlocfilehash: 0acbcb7433c5332dbcb7e183873ea19e660578db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291772"
---
# <a name="single-sign-on-event-10739"></a><span data-ttu-id="c17aa-102">单一登录：事件 10739</span><span class="sxs-lookup"><span data-stu-id="c17aa-102">Single Sign-On: Event 10739</span></span>
## <a name="details"></a><span data-ttu-id="c17aa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c17aa-103">Details</span></span>  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c17aa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c17aa-104">Product Name</span></span>   |                                                                               <span data-ttu-id="c17aa-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c17aa-105">Enterprise Single Sign-On</span></span>                                                                               |
| <span data-ttu-id="c17aa-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c17aa-106">Product Version</span></span> |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    <span data-ttu-id="c17aa-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c17aa-107">Event ID</span></span>     |                                                                                         <span data-ttu-id="c17aa-108">10739</span><span class="sxs-lookup"><span data-stu-id="c17aa-108">10739</span></span>                                                                                         |
|  <span data-ttu-id="c17aa-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c17aa-109">Event Source</span></span>   |                                                                                        <span data-ttu-id="c17aa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c17aa-110">ENTSSO</span></span>                                                                                         |
|    <span data-ttu-id="c17aa-111">组件</span><span class="sxs-lookup"><span data-stu-id="c17aa-111">Component</span></span>    |                                                                                          <span data-ttu-id="c17aa-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c17aa-112">N\A</span></span>                                                                                          |
|  <span data-ttu-id="c17aa-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c17aa-113">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="c17aa-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="c17aa-114">SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER</span></span>                                                                        |
|  <span data-ttu-id="c17aa-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c17aa-115">Message Text</span></span>   | <span data-ttu-id="c17aa-116">更新 SSO database.%r 中的 Windows 密码失败</span><span class="sxs-lookup"><span data-stu-id="c17aa-116">Failed to update the Windows password in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="c17aa-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c17aa-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c17aa-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c17aa-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c17aa-119">Windows 帐户： %3\\%4 %r</span><span class="sxs-lookup"><span data-stu-id="c17aa-119">Windows Account: %3\\%4%r</span></span><br /><br /> <span data-ttu-id="c17aa-120">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="c17aa-120">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="c17aa-121">解释</span><span class="sxs-lookup"><span data-stu-id="c17aa-121">Explanation</span></span>  
 <span data-ttu-id="c17aa-122">此警告事件表示 SSO 更新 SSO 数据库中的 Windows 密码失败。</span><span class="sxs-lookup"><span data-stu-id="c17aa-122">This Warning event indicates that SSO failed to update the Windows password in the SSO database.</span></span> <span data-ttu-id="c17aa-123">有各种可能的原因的指示警告消息; 中失败在某些情况下，此警告可能表示存在配置问题，或映射可能已被删除时密码更改的过程中。</span><span class="sxs-lookup"><span data-stu-id="c17aa-123">There are various possible causes of failure indicated in the warning message; in some cases, this warning might indicate a configuration problem, or the mapping may have been deleted while the password change was in process.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c17aa-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="c17aa-124">User Action</span></span>  
 <span data-ttu-id="c17aa-125">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c17aa-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="c17aa-126">重试更改密码。</span><span class="sxs-lookup"><span data-stu-id="c17aa-126">Retry the password change.</span></span>  

- <span data-ttu-id="c17aa-127">如果更多的尝试仍失败，请使用 UI 或命令行工具手动将密码更改。</span><span class="sxs-lookup"><span data-stu-id="c17aa-127">If additional attempts continue to fail, change the password manually using the UI or command line tools.</span></span>  

  <span data-ttu-id="c17aa-128">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="c17aa-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="c17aa-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="c17aa-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
