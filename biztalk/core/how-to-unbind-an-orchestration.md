---
title: "取消绑定某个业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b8adc77e5e8579339931e49abb501f9981e5fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="unbind-an-orchestration"></a><span data-ttu-id="190a3-102">取消绑定某个业务流程</span><span class="sxs-lookup"><span data-stu-id="190a3-102">Unbind an Orchestration</span></span>

## <a name="overview"></a><span data-ttu-id="190a3-103">概述</span><span class="sxs-lookup"><span data-stu-id="190a3-103">Overview</span></span>
<span data-ttu-id="190a3-104">本主题将介绍如何使用 BizTalk Server 管理控制台从业务流程中删除接收端口绑定、发送端口绑定或主机绑定。</span><span class="sxs-lookup"><span data-stu-id="190a3-104">This topic describes how to use the BizTalk Server Administration console to remove receive port, send port, or host bindings from an orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="190a3-105">应用程序开发人员可以使用本主题中的过程来删除业务流程的绑定。</span><span class="sxs-lookup"><span data-stu-id="190a3-105">The application developer can remove bindings for an orchestration  by using the procedure in this topic.</span></span> <span data-ttu-id="190a3-106">你可以使用 Microsoft Windows Management Instrumentation (WMI) 对象模型来创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="190a3-106">You can also use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="190a3-107">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="190a3-107">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="190a3-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="190a3-108">Prerequisites</span></span>  
 <span data-ttu-id="190a3-109">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="190a3-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="190a3-110">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="190a3-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="remove-bindings-from-an-orchestration"></a><span data-ttu-id="190a3-111">删除从业务流程的绑定</span><span class="sxs-lookup"><span data-stu-id="190a3-111">Remove bindings from an orchestration</span></span>  
  
1.  <span data-ttu-id="190a3-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="190a3-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="190a3-113">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的业务流程的应用程序绑定</span><span class="sxs-lookup"><span data-stu-id="190a3-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration from which you want to remove bindings</span></span>  
  
3.  <span data-ttu-id="190a3-114">单击**业务流程**，右键单击业务流程，单击**属性**，然后单击**绑定**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="190a3-114">Click **Orchestrations**, right-click the orchestration, click **Properties**, and then click **Bindings** in the left pane.</span></span>  
  
4.  <span data-ttu-id="190a3-115">若要删除的主机绑定，**主机**列表中，选择**\<无\>**。</span><span class="sxs-lookup"><span data-stu-id="190a3-115">To remove the host bindings, from the **Hosts** list, select **\<None\>**.</span></span>  
  
5.  <span data-ttu-id="190a3-116">若要删除下的下拉列表从接收端口绑定**接收端口**，单击**\<无\>**。</span><span class="sxs-lookup"><span data-stu-id="190a3-116">To remove receive port bindings, from the drop-down list under **Receive Ports**, click **\<None\>**.</span></span>  
  
6.  <span data-ttu-id="190a3-117">若要从下的下拉列表中删除发送端口绑定**发送端口/发送端口组**，单击**\<无\>**。</span><span class="sxs-lookup"><span data-stu-id="190a3-117">To remove send port bindings, from the drop-down list under **Send Ports/Send Port Groups**, click **\<None\>**.</span></span>  
  
7.  <span data-ttu-id="190a3-118">完成后删除绑定，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="190a3-118">When finished removing bindings, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190a3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="190a3-119">See Also</span></span>  
 <span data-ttu-id="190a3-120">[管理业务流程](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="190a3-120">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="190a3-121">[如何配置适用于业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="190a3-121">[How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md) </span></span>  
 [<span data-ttu-id="190a3-122">部署和管理 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="190a3-122">Deploying and Managing BizTalk Applications</span></span>](../core/deploying-and-managing-biztalk-applications.md)