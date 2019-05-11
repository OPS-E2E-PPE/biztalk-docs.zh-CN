---
title: 如何查看实例信息的接收端口 |Microsoft Docs
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
ms.openlocfilehash: 520e3e5de989f1a9800fab21a31f2997f634d8e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383130"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="d6fe0-102">如何查看实例信息的接收端口</span><span class="sxs-lookup"><span data-stu-id="d6fe0-102">How to View Instance Information for a Receive Port</span></span>
<span data-ttu-id="d6fe0-103">本主题介绍如何使用 BizTalk Server 管理控制台查看接收端口的服务实例。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-103">This topic describes how to use the BizTalk Server Administration console to view the service instances for a receive port.</span></span> <span data-ttu-id="d6fe0-104">接收端口接收消息时，每次创建服务实例来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-104">Each time the receive port receives a message, a service instance is created to process the message.</span></span> <span data-ttu-id="d6fe0-105">当您按照本主题中的过程时，实例信息将显示为接收端口的组概述页中。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6fe0-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="d6fe0-106">Prerequisites</span></span>  
 <span data-ttu-id="d6fe0-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d6fe0-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="d6fe0-109">若要查看实例信息的接收端口</span><span class="sxs-lookup"><span data-stu-id="d6fe0-109">To view instance information for a receive port</span></span>  
  
1. <span data-ttu-id="d6fe0-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d6fe0-111">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要查看实例信息的接收端口。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view instance information for a receive port.</span></span>  
  
3. <span data-ttu-id="d6fe0-112">单击**接收端口**，选择接收端口，单击**视图**，然后单击**实例信息**。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-112">Click **Receive Ports**, select the receive port, click **View**, and then click **Instance Information**.</span></span>  
  
    <span data-ttu-id="d6fe0-113">查询结果窗格中的页的下半部分中显示的接收端口的所有实例。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-113">The query results panel in the lower section of the page displays all instances of the receive port.</span></span>  
  
4. <span data-ttu-id="d6fe0-114">若要修改查询和查看接收端口的其他实例信息，请单击下面的框**值**有关**搜索**字段中，选择要查看，然后单击实例类型**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-114">To refine the query and view different instance information for the receive port, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="d6fe0-115">有关创建查询的详细信息，请参阅另请参阅下面的有关搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="d6fe0-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6fe0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6fe0-116">See Also</span></span>  
 <span data-ttu-id="d6fe0-117">[管理接收端口](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="d6fe0-117">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 <span data-ttu-id="d6fe0-118">[如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="d6fe0-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="d6fe0-119">[如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="d6fe0-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="d6fe0-120">[如何搜索消息](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="d6fe0-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="d6fe0-121">如何搜索订阅</span><span class="sxs-lookup"><span data-stu-id="d6fe0-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)