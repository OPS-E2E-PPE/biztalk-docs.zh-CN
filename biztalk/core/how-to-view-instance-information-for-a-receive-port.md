---
title: 如何查看实例信息接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], viewing
- receive ports, viewing
- viewing, receive ports
ms.assetid: dad038bc-1202-489b-b144-a93bf1f53c0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46da8bfb99246b67f93c02fa19689099f8acb24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256797"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="ee2d1-102">如何查看实例信息接收端口</span><span class="sxs-lookup"><span data-stu-id="ee2d1-102">How to View Instance Information for a Receive Port</span></span>
<span data-ttu-id="ee2d1-103">本主题将介绍如何使用 BizTalk Server 管理控制台查看接收端口的服务实例。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-103">This topic describes how to use the BizTalk Server Administration console to view the service instances for a receive port.</span></span> <span data-ttu-id="ee2d1-104">每次接收端口收到消息，都会创建一个服务实例来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-104">Each time the receive port receives a message, a service instance is created to process the message.</span></span> <span data-ttu-id="ee2d1-105">按照本主题中的过程操作后，实例信息将显示在接收端口的“组概述”页中。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ee2d1-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="ee2d1-106">Prerequisites</span></span>  
 <span data-ttu-id="ee2d1-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="ee2d1-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="ee2d1-109">查看接收端口的实例信息</span><span class="sxs-lookup"><span data-stu-id="ee2d1-109">To view instance information for a receive port</span></span>  
  
1.  <span data-ttu-id="ee2d1-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ee2d1-111">在控制台树中，展开要查看其实例信息的接收端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view instance information for a receive port.</span></span>  
  
3.  <span data-ttu-id="ee2d1-112">单击**接收端口**，选择接收端口中，单击**视图**，然后单击**实例信息**。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-112">Click **Receive Ports**, select the receive port, click **View**, and then click **Instance Information**.</span></span>  
  
     <span data-ttu-id="ee2d1-113">此页下半部分的“查询结果”面板将显示该接收端口的所有实例。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-113">The query results panel in the lower section of the page displays all instances of the receive port.</span></span>  
  
4.  <span data-ttu-id="ee2d1-114">若要优化的查询并查看不同的实例接收端口的信息，请单击下面的框**值**为**搜索**字段中，选择要查看，，然后单击的实例类型**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-114">To refine the query and view different instance information for the receive port, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="ee2d1-115">有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="ee2d1-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2d1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee2d1-116">See Also</span></span>  
 <span data-ttu-id="ee2d1-117">[管理接收端口](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ee2d1-117">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 <span data-ttu-id="ee2d1-118">[如何运行服务实例的搜索](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="ee2d1-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="ee2d1-119">[如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="ee2d1-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="ee2d1-120">[如何搜索消息](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ee2d1-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="ee2d1-121">如何搜索订阅</span><span class="sxs-lookup"><span data-stu-id="ee2d1-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)