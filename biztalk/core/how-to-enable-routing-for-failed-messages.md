---
title: 如何启用的路由失败消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d33beed4-1ae2-4282-95ac-5d68aab7fb5d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e524f96114e887569c10294be0e665f1aa711a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337933"
---
# <a name="how-to-enable-routing-for-failed-messages"></a><span data-ttu-id="8fb12-102">如何为失败消息启用路由功能</span><span class="sxs-lookup"><span data-stu-id="8fb12-102">How to Enable Routing for Failed Messages</span></span>
<span data-ttu-id="8fb12-103">失败的消息路由是一个属性的发送和接收端口和情况下，该值指示"为失败消息启用路由"端口的属性页上启用。</span><span class="sxs-lookup"><span data-stu-id="8fb12-103">Failed message routing is a property of send and receive ports, and is enabled by indicating "Enable routing for failed messages" on the port's property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fb12-104">接收端口上的配置适用于所有与该接收端口相关联的接收位置。</span><span class="sxs-lookup"><span data-stu-id="8fb12-104">The configuration on a receive port applies to all receive locations associated with that receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fb12-105">发送端口上的配置适用于主要和备份传输。</span><span class="sxs-lookup"><span data-stu-id="8fb12-105">The configuration on a send port applies to both the primary and backup transports.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-receive-port-this-applies-to-both-one-way-and-request-response-receive-ports"></a><span data-ttu-id="8fb12-106">若要配置失败的消息路由的接收端口 (这适用于单向和请求-响应接收端口)</span><span class="sxs-lookup"><span data-stu-id="8fb12-106">To configure failed message routing for a receive port (this applies to both one-way and request-response receive ports)</span></span>  
  
1. <span data-ttu-id="8fb12-107">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8fb12-107">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="8fb12-108">展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开该发送端口所属的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8fb12-108">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="8fb12-109">单击**接收端口**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8fb12-109">Click the **Receive Ports** folder.</span></span>  
  
4. <span data-ttu-id="8fb12-110">在右窗格中，双击你想要配置的接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="8fb12-110">In the right pane, double-click the name of the receive port you want to configure.</span></span>  
  
5. <span data-ttu-id="8fb12-111">在接收端口属性页上，在左窗格中，选择**常规**类别。</span><span class="sxs-lookup"><span data-stu-id="8fb12-111">On the receive port's property page, in the left pane, select the **General** category.</span></span>  
  
6. <span data-ttu-id="8fb12-112">在右窗格中，选择**失败消息启用路由功能**复选框，然后依次**应用**。</span><span class="sxs-lookup"><span data-stu-id="8fb12-112">In the right pane, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
### <a name="to-configure-failed-message-routing-for-a-send-port-this-applies-only-to-static-one-way-and-static-solicit-response-send-ports"></a><span data-ttu-id="8fb12-113">若要配置失败消息路由的发送端口 （这仅适用于静态单向和静态要求响应发送端口）</span><span class="sxs-lookup"><span data-stu-id="8fb12-113">To configure failed message routing for a send port (this applies only to static one-way and static solicit-response send ports)</span></span>  
  
1. <span data-ttu-id="8fb12-114">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8fb12-114">Open the BizTalk Server Administration console.</span></span>  
  
2. <span data-ttu-id="8fb12-115">展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开该发送端口所属的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8fb12-115">Expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the application to which the send port belongs.</span></span>  
  
3. <span data-ttu-id="8fb12-116">单击**发送端口**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8fb12-116">Click the **Send Ports** folder.</span></span>  
  
4. <span data-ttu-id="8fb12-117">在右窗格中，双击你想要配置的发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="8fb12-117">In the right pane, double-click the name of the send port you want to configure.</span></span>  
  
5. <span data-ttu-id="8fb12-118">在发送端口的属性页上，在左窗格中，选择**传输高级选项**类别。</span><span class="sxs-lookup"><span data-stu-id="8fb12-118">On the send port's property page, in the left pane, select the **Transport Advanced Options** category.</span></span>  
  
6. <span data-ttu-id="8fb12-119">在右窗格中，在**传输选项**组框中，选择**失败消息启用路由功能**复选框，然后依次**应用**。</span><span class="sxs-lookup"><span data-stu-id="8fb12-119">In the right pane, in the **Transport Options** group box, select the **Enable routing for failed messages** check box, and then click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb12-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fb12-120">See Also</span></span>  
 [<span data-ttu-id="8fb12-121">错误处理</span><span class="sxs-lookup"><span data-stu-id="8fb12-121">Error Handling</span></span>](../core/error-handling.md)