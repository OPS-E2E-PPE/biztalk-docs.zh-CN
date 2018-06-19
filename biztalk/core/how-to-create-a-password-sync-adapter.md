---
title: 如何创建密码同步适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa5bd13-efd9-4544-b5df-17d01c6ac5d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47381cc1ed71788673602c1db7eec5b5ac049ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249365"
---
# <a name="how-to-create-a-password-sync-adapter"></a><span data-ttu-id="1146d-102">如何创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="1146d-102">How to Create a Password Sync Adapter</span></span>
<span data-ttu-id="1146d-103">密码同步 (PS) 适配器是使用密码同步助手组件向企业单一登录 (SSO) 传递通知或从企业单一登录传递通知的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1146d-103">A password sync (PS) adapter is an application that uses the Password Sync Helper component to pass notifications to and from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="1146d-104">请注意，虽然密码同步助手组件公开的是 COM 和 .NET Framework 接口，但适配器并不一定必须为 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="1146d-104">Note that although the PS Helper component exposes a COM and a .NET Framework interface, your adapter does not necessarily have to be a COM component.</span></span> <span data-ttu-id="1146d-105">可以将适配器设计为独立进程、COM+ 应用程序或 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="1146d-105">You can design your adapter as a stand-alone process, a COM+ application, or a Windows service.</span></span>  
  
### <a name="to-create-a-password-sync-adapter"></a><span data-ttu-id="1146d-106">创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="1146d-106">To create a password sync adapter</span></span>  
  
1.  <span data-ttu-id="1146d-107">通知企业单一登录服务 (ENTSSO) 提供程序是活动使用`ISSOPSWrapper.InitializeAdapter`。</span><span class="sxs-lookup"><span data-stu-id="1146d-107">Inform Enterprise Single Sign-On service (ENTSSO) that your provider is active using `ISSOPSWrapper.InitializeAdapter`.</span></span>  
  
     <span data-ttu-id="1146d-108">`InitializeAdapter`提供程序，通常进行调用，同一提供程序当前开启，且因此将通信从系统的密码更新通知 ENTSSO。</span><span class="sxs-lookup"><span data-stu-id="1146d-108">`InitializeAdapter` informs ENTSSO that a provider, usually the same provider that is making the call, is currently turned on, and therefore will be communicating password updates to and from the system.</span></span> <span data-ttu-id="1146d-109">你还可以使用`InitializeAdapter`激活组适配器等资源。</span><span class="sxs-lookup"><span data-stu-id="1146d-109">You can also use `InitializeAdapter` to activate other resources such as group adapters.</span></span>  
  
2.  <span data-ttu-id="1146d-110">通过将密码更新发送给 ENTSSO `ISSOPSWrapper.SendNotification`。</span><span class="sxs-lookup"><span data-stu-id="1146d-110">Send password updates to ENTSSO by using `ISSOPSWrapper.SendNotification`.</span></span>  
  
     <span data-ttu-id="1146d-111">您必须确定如何从非 Windows 系统接收密码更新。</span><span class="sxs-lookup"><span data-stu-id="1146d-111">You must determine how you receive password updates from your non-Windows system.</span></span> <span data-ttu-id="1146d-112">接收更新后，你可以将传递到 ENTSSO 使用信息`SendNotification`。</span><span class="sxs-lookup"><span data-stu-id="1146d-112">After you receive the update, you can pass the information on to ENTSSO using `SendNotification`.</span></span> <span data-ttu-id="1146d-113">请注意，`SendNotification`并不局限于发送密码更新： 的体系结构`SendNotification`还可用于发送其他类型的通知。</span><span class="sxs-lookup"><span data-stu-id="1146d-113">Note that `SendNotification` is not limited to sending password updates: the architecture of `SendNotification` also enables you to send other types of notifications.</span></span>  
  
3.  <span data-ttu-id="1146d-114">通过使用从 ENTSSO 申请密码更新`ISSOPSWrapper.ReceiveNotification`。</span><span class="sxs-lookup"><span data-stu-id="1146d-114">Request password updates from ENTSSO by using `ISSOPSWrapper.ReceiveNotification`.</span></span>  
  
     <span data-ttu-id="1146d-115">由于密码同步适配器采用的是请求技术，因此 ENTSSO 永远也不会调用您的适配器。</span><span class="sxs-lookup"><span data-stu-id="1146d-115">Because the password sync adapter is a pull technology, ENTSSO never calls your adapter.</span></span> <span data-ttu-id="1146d-116">相反，你的适配器定期调用`ReceiveNotification`若要查看是否有任何密码更新可用。</span><span class="sxs-lookup"><span data-stu-id="1146d-116">Instead, your adapter periodically calls `ReceiveNotification` to see whether any password updates are available.</span></span> <span data-ttu-id="1146d-117">你可以选择在上设置等待标志`ReceiveNotification`。</span><span class="sxs-lookup"><span data-stu-id="1146d-117">You can choose to set the WAIT flag on `ReceiveNotification`.</span></span> <span data-ttu-id="1146d-118">设置 WAIT 会阻止该线程，直至有通知可用。</span><span class="sxs-lookup"><span data-stu-id="1146d-118">Setting WAIT blocks the thread until a notification is available.</span></span>  
  
     <span data-ttu-id="1146d-119">请注意，ENTSSO 使用纯文本格式向适配器传递密码更改。</span><span class="sxs-lookup"><span data-stu-id="1146d-119">Note that ENTSSO delivers a password change to your adapter in plain text.</span></span> <span data-ttu-id="1146d-120">适配器负责保护密码信息不致意外泄漏。</span><span class="sxs-lookup"><span data-stu-id="1146d-120">It is the responsibility of the adapter to protect that password information against incorrect disclosure.</span></span> <span data-ttu-id="1146d-121">此外，适配器还要保护自身免遭其他无效源的欺骗或攻击，其中包括密码同步助手组件的欺骗。</span><span class="sxs-lookup"><span data-stu-id="1146d-121">It is also the responsibility of the adapter to protect itself against spoofing or attacks from other invalid sources, including spoofing of the Password Sync Helper component.</span></span>  
  
     <span data-ttu-id="1146d-122">通过 `pReceiveNotification` 参数从 ENTSSO 接收到密码更新之后，您必须将此信息传递到非 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="1146d-122">After you receive a password update from ENTSSO through the `pReceiveNotification` parameter, you must pass this information on to your non-Windows system.</span></span> <span data-ttu-id="1146d-123">与`SendNotification`，必须确定与远程服务器通信的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="1146d-123">As with `SendNotification`, you must determine the best way to communicate with the remote server.</span></span>  
  
4.  <span data-ttu-id="1146d-124">关闭你适配器使用`ISSOPSWrapper.ShutdownAdapter`。</span><span class="sxs-lookup"><span data-stu-id="1146d-124">Turn off your adapter using `ISSOPSWrapper.ShutdownAdapter`.</span></span>  
  
     <span data-ttu-id="1146d-125">`ShutdownApplication`应为最后一个方法调用由适配器，并指示该适配器将不再发送或接收到 ENTSSO 的密码更新。</span><span class="sxs-lookup"><span data-stu-id="1146d-125">`ShutdownApplication` should be the last method called by an adapter, and indicates that the adapter will no longer send or receive password updates to ENTSSO.</span></span>  
  
     <span data-ttu-id="1146d-126">请注意，在关闭适配器后，ENTSSO 仍会缓存用户所做的所有密码更改，直到达到缓冲区大小限制。</span><span class="sxs-lookup"><span data-stu-id="1146d-126">Note that ENTSSO buffers any password changes a user makes while the adapter is shut down, up to a buffer size limit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1146d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1146d-127">See Also</span></span>  
 <span data-ttu-id="1146d-128">[使用企业单一登录进行编程](../core/programming-with-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="1146d-128">[Programming with Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md) </span></span>  
 [<span data-ttu-id="1146d-129">同步密码</span><span class="sxs-lookup"><span data-stu-id="1146d-129">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)