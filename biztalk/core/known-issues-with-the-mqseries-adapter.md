---
title: "已知问题 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe3093416a10b6b66867dcb2e3629de8f25e5aca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-mqseries-adapter"></a><span data-ttu-id="a785b-102">MQSeries 适配器已知问题</span><span class="sxs-lookup"><span data-stu-id="a785b-102">Known Issues with the MQSeries Adapter</span></span>
<span data-ttu-id="a785b-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="a785b-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="know-issues"></a><span data-ttu-id="a785b-104">了解问题</span><span class="sxs-lookup"><span data-stu-id="a785b-104">Know Issues</span></span>  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a><span data-ttu-id="a785b-105">尝试发送或接收消息时，发生访问被拒绝错误</span><span class="sxs-lookup"><span data-stu-id="a785b-105">Access Denied errors occur when attempting to send or receive messages</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="a785b-106">问题</span><span class="sxs-lookup"><span data-stu-id="a785b-106">Problem</span></span>  
 <span data-ttu-id="a785b-107">使用 MQSeries 适配器向 MQSeries 服务器发送消息或从 MQSeries 适配器接收消息时，在事件查看器中查看时会发现应用程序日志中记录类似于以下内容的错误消息：</span><span class="sxs-lookup"><span data-stu-id="a785b-107">When you use the MQSeries adapter to send messages to or receive messages from an MQSeries server, error messages that are similar to the following are logged in the Application log in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  <span data-ttu-id="a785b-108">在此错误消息中， *servername*是服务器的名称和*queuename*是队列的名称。</span><span class="sxs-lookup"><span data-stu-id="a785b-108">In this error message, *servername* is the name of the server and *queuename* is the name of the queue.</span></span>  
  
 <span data-ttu-id="a785b-109">另外，在尝试创建接收位置或发送端口（配置为使用用于 MQSeries 的 BizTalk 适配器）时，可能会在事件查看器中收到以下警告消息：</span><span class="sxs-lookup"><span data-stu-id="a785b-109">Additionally, when you try to create the receive location or the send port that is configured to use the BizTalk Adapter for MQSeries, you may receive the following warning message in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a><span data-ttu-id="a785b-110">原因</span><span class="sxs-lookup"><span data-stu-id="a785b-110">Cause</span></span>  
 <span data-ttu-id="a785b-111">如果满足以下一个或多个条件，就会出现此问题：</span><span class="sxs-lookup"><span data-stu-id="a785b-111">This issue may occur if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="a785b-112">MQSeries 适配器的主机帐户没有 MQSeries 服务器上 MQSAgent COM+ 应用程序必需的权限。</span><span class="sxs-lookup"><span data-stu-id="a785b-112">The host account for the MQSeries adapter does not have the required permissions for the MQSAgent COM+ application on the MQSeries server.</span></span>  
  
-   <span data-ttu-id="a785b-113">在基于 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的服务器上，MQSeries 适配器的主机帐户不是 MQSeries 服务器上 Distributed COM Users 组的成员。</span><span class="sxs-lookup"><span data-stu-id="a785b-113">On a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, the host account for the MQSeries adapter is not a member of the Distributed COM Users group on the MQSeries server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="a785b-114">解决方法</span><span class="sxs-lookup"><span data-stu-id="a785b-114">Resolution</span></span>  
 <span data-ttu-id="a785b-115">若要解决此问题，请使用以下方法。</span><span class="sxs-lookup"><span data-stu-id="a785b-115">To resolve this issue, use the following methods.</span></span> <span data-ttu-id="a785b-116">如果一种方法不能解决问题，请尝试另一种方法。</span><span class="sxs-lookup"><span data-stu-id="a785b-116">If a method does not resolve the issue, try the next method.</span></span>  
  
 <span data-ttu-id="a785b-117">**方法 1： 启用 microsoft 网络 COM + 访问[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于计算机**</span><span class="sxs-lookup"><span data-stu-id="a785b-117">**Method 1: Enable network COM+ access on the Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer**</span></span>  
  
 <span data-ttu-id="a785b-118">启用 Microsoft 网络 COM + 访问[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-按照所述的步骤基于计算机[如何启用 Windows Server 2003 中的网络 COM + 访问](http://go.microsoft.com/fwlink/?LinkId=67076)。</span><span class="sxs-lookup"><span data-stu-id="a785b-118">Enable network COM+ access on a Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer by following the steps documented in [How to enable network COM+ access in Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).</span></span>  
  
 <span data-ttu-id="a785b-119">**方法 2： 配置 MSDTC 设置**</span><span class="sxs-lookup"><span data-stu-id="a785b-119">**Method 2: Configure MSDTC settings**</span></span>  
  
 <span data-ttu-id="a785b-120">按照中的步骤**上设置适当的 MSDTC 的安全配置选项[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]**部分[问题疑难解答与 MSDTC](../core/troubleshooting-problems-with-msdtc.md)配置 MSDTC 设置。</span><span class="sxs-lookup"><span data-stu-id="a785b-120">Follow the steps in the **Set the appropriate MSDTC Security Configuration options on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** section of [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to configure MSDTC settings.</span></span>  
  
 <span data-ttu-id="a785b-121">**方法 3： 验证主机帐户已添加到 MQSAgent COM + 应用程序中的角色**</span><span class="sxs-lookup"><span data-stu-id="a785b-121">**Method 3: Verify that the host account is added to the role in the MQSAgent COM+ application**</span></span>  
  
 <span data-ttu-id="a785b-122">验证是否已将 MQSeries 适配器的主机帐户添加到在 MQSeries 服务器的 MQSAgent COM+ 应用程序中所创建的角色。</span><span class="sxs-lookup"><span data-stu-id="a785b-122">Verify that the host account for the MQSeries adapter is added to the role that was created in the MQSAgent COM+ application on the MQSeries server.</span></span> <span data-ttu-id="a785b-123">可以在组件服务管理控制台界面中进行验证。</span><span class="sxs-lookup"><span data-stu-id="a785b-123">You can verify this in the Component Services management console interface.</span></span>  
  
 <span data-ttu-id="a785b-124">**方法 4： 验证 MQSeries 适配器的主机帐户 Distributed COM Users 组的成员**</span><span class="sxs-lookup"><span data-stu-id="a785b-124">**Method 4: Verify that the host account for the MQSeries adapter is a member of the Distributed COM Users group**</span></span>  
  
 <span data-ttu-id="a785b-125">在基于 Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的服务器上，检查 MQSeries 适配器的主机帐户的组成员关系。</span><span class="sxs-lookup"><span data-stu-id="a785b-125">On a Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, examine the group memberships of the host account for the MQSeries adapter.</span></span> <span data-ttu-id="a785b-126">请确保该帐户的成员**Distributed COM Users** MQSAgent COM + 应用程序的安装位置的 MQSeries 服务器组。</span><span class="sxs-lookup"><span data-stu-id="a785b-126">Make sure that the account is a member of the **Distributed COM Users** group on the MQSeries server where the MQSAgent COM+ application is installed.</span></span>  
  
 <span data-ttu-id="a785b-127">有关在 Microsoft 中的 DCOM 安全增强功能的详细信息[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请参阅[DCOM 安全增强功能](http://go.microsoft.com/fwlink/?LinkId=67077)。</span><span class="sxs-lookup"><span data-stu-id="a785b-127">For more information about DCOM security enhancements in Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], see [DCOM Security Enhancements](http://go.microsoft.com/fwlink/?LinkId=67077).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a785b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a785b-128">See Also</span></span>  
 [<span data-ttu-id="a785b-129">故障排除 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="a785b-129">Troubleshooting the MQSeries Adapter</span></span>](../core/troubleshooting-the-mqseries-adapter.md)