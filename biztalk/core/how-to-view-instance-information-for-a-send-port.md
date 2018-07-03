---
title: 如何查看发送端口的实例信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc1ae4401303845f92b95e6cdf7f4903c165b07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975142"
---
# <a name="how-to-view-instance-information-for-a-send-port"></a><span data-ttu-id="60477-102">如何查看发送端口的实例信息</span><span class="sxs-lookup"><span data-stu-id="60477-102">How to View Instance Information for a Send Port</span></span>
<span data-ttu-id="60477-103">本主题将介绍如何使用 BizTalk Server 管理控制台来查看发送端口的正在运行的服务实例列表。</span><span class="sxs-lookup"><span data-stu-id="60477-103">This topic describes how to use the BizTalk Server Administration console to view a list of the running service instances of a send port.</span></span> <span data-ttu-id="60477-104">服务实例是在消息被发送到发送端口时创建的发送端口服务实例。</span><span class="sxs-lookup"><span data-stu-id="60477-104">A service instance is an instance of the send port service that is created when a message is sent to the send port.</span></span> <span data-ttu-id="60477-105">按照本主题中的过程操作后，实例信息将显示在发送端口的“组概述”页中。</span><span class="sxs-lookup"><span data-stu-id="60477-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60477-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="60477-106">Prerequisites</span></span>  
 <span data-ttu-id="60477-107">若要执行本主题中描述的过程，必须以 BizTalk Server Administrators 组或 BizTalk Server Operators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="60477-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="60477-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="60477-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-send-port"></a><span data-ttu-id="60477-109">查看发送端口的实例信息</span><span class="sxs-lookup"><span data-stu-id="60477-109">To view instance information for a send port</span></span>  
  
1. <span data-ttu-id="60477-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="60477-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="60477-111">在控制台树中，展开要查看其服务实例信息的发送端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="60477-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view service instance information for a send port.</span></span>  
  
3. <span data-ttu-id="60477-112">单击**发送端口**，右键单击发送端口，指向**视图**，然后单击**实例信息**。</span><span class="sxs-lookup"><span data-stu-id="60477-112">Click **Send Ports**, right-click the send port, point to **View**, and then click **Instance Information**.</span></span>  
  
    <span data-ttu-id="60477-113">此页下半部分的“查询结果”面板将显示发送端口的所有运行实例。</span><span class="sxs-lookup"><span data-stu-id="60477-113">The query results panel in the lower section of the page displays all running instances of the send port.</span></span>  
  
4. <span data-ttu-id="60477-114">若要修改查询和查看发送端口的不同的服务实例信息，请单击下面的方框**值**的搜索字段中，选择要查看，然后单击实例类型**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="60477-114">To refine the query and view different service instance information for the send port, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="60477-115">有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="60477-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60477-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="60477-116">See Also</span></span>  
 <span data-ttu-id="60477-117">[创建和配置发送端口](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="60477-117">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 <span data-ttu-id="60477-118">[如何搜索正在运行的服务实例](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="60477-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="60477-119">[如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="60477-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="60477-120">[如何搜索消息](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="60477-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="60477-121">如何搜索订阅</span><span class="sxs-lookup"><span data-stu-id="60477-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)