---
title: 如何创建密码同步适配器 |Microsoft Docs
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
ms.openlocfilehash: a2c3ca305f86f541bd1cb681ed97aea7768e77c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339932"
---
# <a name="how-to-create-a-password-sync-adapter"></a><span data-ttu-id="399d8-102">如何创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="399d8-102">How to Create a Password Sync Adapter</span></span>
<span data-ttu-id="399d8-103">密码同步 (PS) 适配器是使用密码同步助手组件传递通知到和从企业单一登录 (SSO) 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="399d8-103">A password sync (PS) adapter is an application that uses the Password Sync Helper component to pass notifications to and from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="399d8-104">请注意，尽管 PS 助手组件公开的 COM 和.NET Framework 接口，您的适配器不会不一定必须是 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="399d8-104">Note that although the PS Helper component exposes a COM and a .NET Framework interface, your adapter does not necessarily have to be a COM component.</span></span> <span data-ttu-id="399d8-105">您可以设计您的适配器作为独立进程、 COM + 应用程序，或者 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="399d8-105">You can design your adapter as a stand-alone process, a COM+ application, or a Windows service.</span></span>  
  
### <a name="to-create-a-password-sync-adapter"></a><span data-ttu-id="399d8-106">若要创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="399d8-106">To create a password sync adapter</span></span>  
  
1.  <span data-ttu-id="399d8-107">通知企业单一登录服务 (ENTSSO) 您的提供程序是活动使用`ISSOPSWrapper.InitializeAdapter`。</span><span class="sxs-lookup"><span data-stu-id="399d8-107">Inform Enterprise Single Sign-On service (ENTSSO) that your provider is active using `ISSOPSWrapper.InitializeAdapter`.</span></span>  
  
     <span data-ttu-id="399d8-108">`InitializeAdapter` 通知 ENTSSO 提供程序，通常进行调用，同一提供程序当前已打开，并因此将通信从系统的密码更新。</span><span class="sxs-lookup"><span data-stu-id="399d8-108">`InitializeAdapter` informs ENTSSO that a provider, usually the same provider that is making the call, is currently turned on, and therefore will be communicating password updates to and from the system.</span></span> <span data-ttu-id="399d8-109">此外可以使用`InitializeAdapter`激活其他资源，例如组适配器。</span><span class="sxs-lookup"><span data-stu-id="399d8-109">You can also use `InitializeAdapter` to activate other resources such as group adapters.</span></span>  
  
2.  <span data-ttu-id="399d8-110">使用向 ENTSSO 发送密码更新`ISSOPSWrapper.SendNotification`。</span><span class="sxs-lookup"><span data-stu-id="399d8-110">Send password updates to ENTSSO by using `ISSOPSWrapper.SendNotification`.</span></span>  
  
     <span data-ttu-id="399d8-111">您必须确定如何从非 Windows 系统接收密码更新。</span><span class="sxs-lookup"><span data-stu-id="399d8-111">You must determine how you receive password updates from your non-Windows system.</span></span> <span data-ttu-id="399d8-112">接收到更新后，可以将传递到 entsso 之间使用的信息`SendNotification`。</span><span class="sxs-lookup"><span data-stu-id="399d8-112">After you receive the update, you can pass the information on to ENTSSO using `SendNotification`.</span></span> <span data-ttu-id="399d8-113">请注意，`SendNotification`并不仅限于发送密码更新： 的体系结构`SendNotification`还可以发送其他类型的通知。</span><span class="sxs-lookup"><span data-stu-id="399d8-113">Note that `SendNotification` is not limited to sending password updates: the architecture of `SendNotification` also enables you to send other types of notifications.</span></span>  
  
3.  <span data-ttu-id="399d8-114">通过使用从 ENTSSO 请求密码更新`ISSOPSWrapper.ReceiveNotification`。</span><span class="sxs-lookup"><span data-stu-id="399d8-114">Request password updates from ENTSSO by using `ISSOPSWrapper.ReceiveNotification`.</span></span>  
  
     <span data-ttu-id="399d8-115">由于密码同步适配器的是请求技术，因此 ENTSSO 永远不会调用您的适配器。</span><span class="sxs-lookup"><span data-stu-id="399d8-115">Because the password sync adapter is a pull technology, ENTSSO never calls your adapter.</span></span> <span data-ttu-id="399d8-116">相反，适配器定期调用`ReceiveNotification`以查看是否有可用的任何密码更新。</span><span class="sxs-lookup"><span data-stu-id="399d8-116">Instead, your adapter periodically calls `ReceiveNotification` to see whether any password updates are available.</span></span> <span data-ttu-id="399d8-117">您可以选择对设置 WAIT 标志`ReceiveNotification`。</span><span class="sxs-lookup"><span data-stu-id="399d8-117">You can choose to set the WAIT flag on `ReceiveNotification`.</span></span> <span data-ttu-id="399d8-118">设置 WAIT 会阻止线程，直至有通知可用。</span><span class="sxs-lookup"><span data-stu-id="399d8-118">Setting WAIT blocks the thread until a notification is available.</span></span>  
  
     <span data-ttu-id="399d8-119">请注意 ENTSSO 到适配器以纯文本形式传递密码更改。</span><span class="sxs-lookup"><span data-stu-id="399d8-119">Note that ENTSSO delivers a password change to your adapter in plain text.</span></span> <span data-ttu-id="399d8-120">它负责保护密码信息不致意外泄漏的适配器。</span><span class="sxs-lookup"><span data-stu-id="399d8-120">It is the responsibility of the adapter to protect that password information against incorrect disclosure.</span></span> <span data-ttu-id="399d8-121">它也是保护自身免遭欺骗的适配器的责任，或从其他无效源，包括密码同步助手组件的欺骗攻击。</span><span class="sxs-lookup"><span data-stu-id="399d8-121">It is also the responsibility of the adapter to protect itself against spoofing or attacks from other invalid sources, including spoofing of the Password Sync Helper component.</span></span>  
  
     <span data-ttu-id="399d8-122">从通过 ENTSSO 接收到密码更新之后`pReceiveNotification`参数，必须将此信息传递到非 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="399d8-122">After you receive a password update from ENTSSO through the `pReceiveNotification` parameter, you must pass this information on to your non-Windows system.</span></span> <span data-ttu-id="399d8-123">与使用`SendNotification`，必须确定与远程服务器通信的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="399d8-123">As with `SendNotification`, you must determine the best way to communicate with the remote server.</span></span>  
  
4.  <span data-ttu-id="399d8-124">关闭适配器使用`ISSOPSWrapper.ShutdownAdapter`。</span><span class="sxs-lookup"><span data-stu-id="399d8-124">Turn off your adapter using `ISSOPSWrapper.ShutdownAdapter`.</span></span>  
  
     <span data-ttu-id="399d8-125">`ShutdownApplication` 应为最后一个方法由适配器调用，并指示该适配器将无法再发送或接收到 ENTSSO 密码更新。</span><span class="sxs-lookup"><span data-stu-id="399d8-125">`ShutdownApplication` should be the last method called by an adapter, and indicates that the adapter will no longer send or receive password updates to ENTSSO.</span></span>  
  
     <span data-ttu-id="399d8-126">请注意 ENTSSO 缓冲用户使适配器关闭的情况下，最多的缓冲区大小限制为任何密码更改。</span><span class="sxs-lookup"><span data-stu-id="399d8-126">Note that ENTSSO buffers any password changes a user makes while the adapter is shut down, up to a buffer size limit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399d8-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="399d8-127">See Also</span></span>  
 <span data-ttu-id="399d8-128">[使用企业单一登录进行编程](../core/programming-with-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="399d8-128">[Programming with Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md) </span></span>  
 [<span data-ttu-id="399d8-129">同步密码</span><span class="sxs-lookup"><span data-stu-id="399d8-129">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)