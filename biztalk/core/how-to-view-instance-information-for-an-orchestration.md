---
title: 如何查看为业务流程的实例信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84129d48fba15dadfc97722ead85b1535a8fa597
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256525"
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="3767a-102">如何查看为业务流程的实例信息</span><span class="sxs-lookup"><span data-stu-id="3767a-102">How to View Instance Information for an Orchestration</span></span>
<span data-ttu-id="3767a-103">本主题介绍如何使用 BizTalk Server 管理控制台来查看业务流程的实例信息。</span><span class="sxs-lookup"><span data-stu-id="3767a-103">This topic describes how to view instance information for an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="3767a-104">服务实例是 BizTalk Server 正在处理或已经序列化到 MessageBox 中以便进一步处理或跟踪的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="3767a-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or has serialized into the MessageBox for further processing or tracking.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3767a-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3767a-105">Prerequisites</span></span>  
 <span data-ttu-id="3767a-106">若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3767a-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3767a-107">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3767a-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="3767a-108">查看业务流程的实例信息</span><span class="sxs-lookup"><span data-stu-id="3767a-108">To view instance information for an orchestration</span></span>  
  
1.  <span data-ttu-id="3767a-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3767a-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3767a-110">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要查看实例信息业务的流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3767a-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to view instance information.</span></span>  
  
3.  <span data-ttu-id="3767a-111">单击**业务流程**，选择你想要查看实例信息、 业务的流程单击**视图**，然后选择**实例信息**。</span><span class="sxs-lookup"><span data-stu-id="3767a-111">Click **Orchestrations**, select the orchestration for which you want to view instance information, click **View**, and then select **Instance Information**.</span></span>  
  
     <span data-ttu-id="3767a-112">此页下半部分的“查询结果”面板将显示该业务流程的所有实例。</span><span class="sxs-lookup"><span data-stu-id="3767a-112">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
     <span data-ttu-id="3767a-113">若要优化业务流程的查询和查看不同的实例信息，请单击下面的框**值**对于的搜索字段中，选择要查看，，然后单击的实例类型**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="3767a-113">To refine the query and view different instance information for the orchestration, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="3767a-114">有关创建查询的详细信息，请参阅“另请参见”下面的有关搜索的主题。</span><span class="sxs-lookup"><span data-stu-id="3767a-114">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3767a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3767a-115">See Also</span></span>  
 <span data-ttu-id="3767a-116">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="3767a-116">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="3767a-117">[如何运行服务实例的搜索](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="3767a-117">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="3767a-118">[如何搜索挂起的服务实例](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="3767a-118">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="3767a-119">[如何搜索消息](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3767a-119">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="3767a-120">如何搜索订阅</span><span class="sxs-lookup"><span data-stu-id="3767a-120">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)