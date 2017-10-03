---
title: "单一登录： 事件 10708 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d600c39b2e79e619e5adfbda2ffc152169ccd5d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10708"></a><span data-ttu-id="60a21-102">单一登录： 事件 10708</span><span class="sxs-lookup"><span data-stu-id="60a21-102">Single Sign-On: Event 10708</span></span>
## <a name="details"></a><span data-ttu-id="60a21-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="60a21-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60a21-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="60a21-104">Product Name</span></span>|<span data-ttu-id="60a21-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="60a21-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="60a21-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="60a21-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="60a21-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="60a21-107">Event ID</span></span>|<span data-ttu-id="60a21-108">10708</span><span class="sxs-lookup"><span data-stu-id="60a21-108">10708</span></span>|  
|<span data-ttu-id="60a21-109">事件源</span><span class="sxs-lookup"><span data-stu-id="60a21-109">Event Source</span></span>|<span data-ttu-id="60a21-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="60a21-110">ENTSSO</span></span>|  
|<span data-ttu-id="60a21-111">组件</span><span class="sxs-lookup"><span data-stu-id="60a21-111">Component</span></span>|<span data-ttu-id="60a21-112">N\A</span><span class="sxs-lookup"><span data-stu-id="60a21-112">N\A</span></span>|  
|<span data-ttu-id="60a21-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="60a21-113">Symbolic Name</span></span>|<span data-ttu-id="60a21-114">SSO_WARN_PS_NO_WIN_SYNC</span><span class="sxs-lookup"><span data-stu-id="60a21-114">SSO_WARN_PS_NO_WIN_SYNC</span></span>|  
|<span data-ttu-id="60a21-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="60a21-115">Message Text</span></span>|<span data-ttu-id="60a21-116">不允许从 Windows 进行密码同步。</span><span class="sxs-lookup"><span data-stu-id="60a21-116">Password sync from Windows is not allowed.</span></span> <span data-ttu-id="60a21-117">请检查全局标志。%r</span><span class="sxs-lookup"><span data-stu-id="60a21-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="60a21-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="60a21-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="60a21-119">客户端用户： %2</span><span class="sxs-lookup"><span data-stu-id="60a21-119">Client User: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60a21-120">解释</span><span class="sxs-lookup"><span data-stu-id="60a21-120">Explanation</span></span>  
 <span data-ttu-id="60a21-121">此警告事件表明 Windows 请求进行密码同步并且未设置任何全局标志。</span><span class="sxs-lookup"><span data-stu-id="60a21-121">This Warning event indicates that password sync is requested by Windows and neither of the global flags is set.</span></span> <span data-ttu-id="60a21-122">有两个标志，允许发送到外部系统的密码： SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL，另一个允许接收来自外部系统 SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB 的密码。</span><span class="sxs-lookup"><span data-stu-id="60a21-122">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60a21-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="60a21-123">User Action</span></span>  
 <span data-ttu-id="60a21-124">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="60a21-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="60a21-125">使用 SSO 管理 MMC 管理单元中，(系统 &#124;属性 &#124;选项） 或命令行工具`ssomanage –enable winsync/extsync`若要启用的全局标志。</span><span class="sxs-lookup"><span data-stu-id="60a21-125">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="60a21-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="60a21-126">More info</span></span>
  
-   <span data-ttu-id="60a21-127">**企业单一登录标志**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="60a21-127">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="60a21-128">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="60a21-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)