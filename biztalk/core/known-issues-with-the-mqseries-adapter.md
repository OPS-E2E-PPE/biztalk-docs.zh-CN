---
title: 使用 MQSeries 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6185519c3669b61a805fb403b38ead9ad6316184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380897"
---
# <a name="known-issues-with-the-mqseries-adapter"></a><span data-ttu-id="d1c47-102">MQSeries 适配器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="d1c47-102">Known Issues with the MQSeries Adapter</span></span>
<span data-ttu-id="d1c47-103">本部分包含可能帮助您避免错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d1c47-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="know-issues"></a><span data-ttu-id="d1c47-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="d1c47-104">Know Issues</span></span>  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a><span data-ttu-id="d1c47-105">尝试发送或接收消息时，发生访问被拒绝错误</span><span class="sxs-lookup"><span data-stu-id="d1c47-105">Access Denied errors occur when attempting to send or receive messages</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d1c47-106">问题</span><span class="sxs-lookup"><span data-stu-id="d1c47-106">Problem</span></span>  
 <span data-ttu-id="d1c47-107">当使用 MQSeries 适配器将消息发送到或从 MQSeries 服务器接收消息时，在事件查看器应用程序日志中记录类似于以下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="d1c47-107">When you use the MQSeries adapter to send messages to or receive messages from an MQSeries server, error messages that are similar to the following are logged in the Application log in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  <span data-ttu-id="d1c47-108">此错误消息中， *servername*是服务器的名称和*queuename*是队列的名称。</span><span class="sxs-lookup"><span data-stu-id="d1c47-108">In this error message, *servername* is the name of the server and *queuename* is the name of the queue.</span></span>  
  
 <span data-ttu-id="d1c47-109">此外，当您尝试创建接收位置或配置为使用用于 MQSeries 的 BizTalk 适配器的发送端口，您可能会在事件查看器中收到以下警告消息：</span><span class="sxs-lookup"><span data-stu-id="d1c47-109">Additionally, when you try to create the receive location or the send port that is configured to use the BizTalk Adapter for MQSeries, you may receive the following warning message in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a><span data-ttu-id="d1c47-110">原因</span><span class="sxs-lookup"><span data-stu-id="d1c47-110">Cause</span></span>  
 <span data-ttu-id="d1c47-111">可能出现此问题，如果一个或多个以下条件成立：</span><span class="sxs-lookup"><span data-stu-id="d1c47-111">This issue may occur if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="d1c47-112">MQSeries 适配器的主机帐户没有 MQSeries 服务器的 MQSAgent COM + 应用程序所需的权限。</span><span class="sxs-lookup"><span data-stu-id="d1c47-112">The host account for the MQSeries adapter does not have the required permissions for the MQSAgent COM+ application on the MQSeries server.</span></span>  
  
- <span data-ttu-id="d1c47-113">上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-MQSeries 适配器不是 MQSeries 服务器上 Distributed COM Users 组的成员的基于服务器的主机帐户。</span><span class="sxs-lookup"><span data-stu-id="d1c47-113">On a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, the host account for the MQSeries adapter is not a member of the Distributed COM Users group on the MQSeries server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d1c47-114">解决方法</span><span class="sxs-lookup"><span data-stu-id="d1c47-114">Resolution</span></span>  
 <span data-ttu-id="d1c47-115">若要解决此问题，请使用以下方法。</span><span class="sxs-lookup"><span data-stu-id="d1c47-115">To resolve this issue, use the following methods.</span></span> <span data-ttu-id="d1c47-116">如果一种方法无法解决此问题，请尝试下一个方法。</span><span class="sxs-lookup"><span data-stu-id="d1c47-116">If a method does not resolve the issue, try the next method.</span></span>  
  
 <span data-ttu-id="d1c47-117">**方法 1:启用网络 COM + 访问 microsoft[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于计算机**</span><span class="sxs-lookup"><span data-stu-id="d1c47-117">**Method 1: Enable network COM+ access on the Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer**</span></span>  
  
 <span data-ttu-id="d1c47-118">Microsoft 上启用网络 COM + 访问[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于计算机中所述的步骤[如何在 Windows Server 2003 启用网络 COM + 访问](http://go.microsoft.com/fwlink/?LinkId=67076)。</span><span class="sxs-lookup"><span data-stu-id="d1c47-118">Enable network COM+ access on a Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer by following the steps documented in [How to enable network COM+ access in Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).</span></span>  
  
 <span data-ttu-id="d1c47-119">**方法 2:配置 MSDTC 设置**</span><span class="sxs-lookup"><span data-stu-id="d1c47-119">**Method 2: Configure MSDTC settings**</span></span>  
  
 <span data-ttu-id="d1c47-120">按照中的步骤**上设置相应的 MSDTC 安全配置选项[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** 一部分[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)配置 MSDTC 设置。</span><span class="sxs-lookup"><span data-stu-id="d1c47-120">Follow the steps in the **Set the appropriate MSDTC Security Configuration options on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** section of [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to configure MSDTC settings.</span></span>  
  
 <span data-ttu-id="d1c47-121">**方法 3:验证将主机帐户添加到 MQSAgent COM + 应用程序中的角色**</span><span class="sxs-lookup"><span data-stu-id="d1c47-121">**Method 3: Verify that the host account is added to the role in the MQSAgent COM+ application**</span></span>  
  
 <span data-ttu-id="d1c47-122">验证 MQSeries 适配器的主机帐户添加到在 MQSeries 服务器上的 MQSAgent COM + 应用程序中创建的角色。</span><span class="sxs-lookup"><span data-stu-id="d1c47-122">Verify that the host account for the MQSeries adapter is added to the role that was created in the MQSAgent COM+ application on the MQSeries server.</span></span> <span data-ttu-id="d1c47-123">可以将此验证，请在组件服务管理控制台界面中。</span><span class="sxs-lookup"><span data-stu-id="d1c47-123">You can verify this in the Component Services management console interface.</span></span>  
  
 <span data-ttu-id="d1c47-124">**方法 4:验证 MQSeries 适配器的主机帐户为 Distributed COM Users 组的成员**</span><span class="sxs-lookup"><span data-stu-id="d1c47-124">**Method 4: Verify that the host account for the MQSeries adapter is a member of the Distributed COM Users group**</span></span>  
  
 <span data-ttu-id="d1c47-125">在 Windows 上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-基于服务器上，检查 MQSeries 适配器的主机帐户的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d1c47-125">On a Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, examine the group memberships of the host account for the MQSeries adapter.</span></span> <span data-ttu-id="d1c47-126">请确保该帐户的成员**Distributed COM Users**安装 MQSAgent COM + 应用程序的 MQSeries 服务器组。</span><span class="sxs-lookup"><span data-stu-id="d1c47-126">Make sure that the account is a member of the **Distributed COM Users** group on the MQSeries server where the MQSAgent COM+ application is installed.</span></span>  
  
 <span data-ttu-id="d1c47-127">有关在 Microsoft 中 DCOM 安全性增强功能的详细信息[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请参阅[DCOM 安全增强功能](http://go.microsoft.com/fwlink/?LinkId=67077)。</span><span class="sxs-lookup"><span data-stu-id="d1c47-127">For more information about DCOM security enhancements in Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], see [DCOM Security Enhancements](http://go.microsoft.com/fwlink/?LinkId=67077).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c47-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1c47-128">See Also</span></span>  
 [<span data-ttu-id="d1c47-129">MQSeries 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="d1c47-129">Troubleshooting the MQSeries Adapter</span></span>](../core/troubleshooting-the-mqseries-adapter.md)