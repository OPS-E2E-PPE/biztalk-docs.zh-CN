---
title: 如何将服务器添加到组 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- adding, servers
- managing [groups], adding servers
- servers, groups
- managing [servers], adding to groups
ms.assetid: 6eca1eeb-1a56-4470-b3bc-c64865cf6270
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db5c7b760167f3e17d3ea82bf1023884b65e725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247677"
---
# <a name="how-to-add-a-server-to-a-group"></a><span data-ttu-id="90177-102">如何将服务器添加到组</span><span class="sxs-lookup"><span data-stu-id="90177-102">How to Add a Server to a Group</span></span>
<span data-ttu-id="90177-103">您可以使用 BizTalk Server 配置向 BizTalk 组添加服务器。</span><span class="sxs-lookup"><span data-stu-id="90177-103">You can use BizTalk Server Configuration to add a server to a BizTalk group.</span></span> <span data-ttu-id="90177-104">通过向 BizTalk 组添加其他服务器可以对 BizTalk Server 环境进行扩展。</span><span class="sxs-lookup"><span data-stu-id="90177-104">You add additional servers to a BizTalk group to scale out your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="90177-105">一台服务器只能与一个 BizTalk 组相关联。</span><span class="sxs-lookup"><span data-stu-id="90177-105">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="90177-106">如果某个服务器已属于其他组，则必须首先从其当前组中删除该服务器，然后才可以将该服务器添加到新的组。</span><span class="sxs-lookup"><span data-stu-id="90177-106">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span> <span data-ttu-id="90177-107">有关从 BizTalk 组中删除服务器的信息，请参阅[如何从组中删除服务器](../core/how-to-remove-a-server-from-a-group.md)。</span><span class="sxs-lookup"><span data-stu-id="90177-107">For information about removing a server from a BizTalk group, see [How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90177-108">与 BizTalk Server 环境中不同服务器关联的 BizTalk 组除交换消息之外不会进行任何其他交互。</span><span class="sxs-lookup"><span data-stu-id="90177-108">BizTalk groups associated with different servers in a BizTalk Server environment do not interact except to exchange messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="90177-109">必须在要添加到 BizTalk 组的计算机上安装 BizTalk Server 运行时。</span><span class="sxs-lookup"><span data-stu-id="90177-109">The BizTalk Server runtime must be installed on the computer you want to add to the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="90177-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="90177-110">Prerequisites</span></span>  
 <span data-ttu-id="90177-111">若要执行此过程，必须以 SSO Administrators 组成员和 Windows Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="90177-111">To perform this procedure, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a><span data-ttu-id="90177-112">向 BizTalk 组添加服务器</span><span class="sxs-lookup"><span data-stu-id="90177-112">To add a server to a BizTalk group</span></span>  
  
1.  <span data-ttu-id="90177-113">在你想要添加到 BizTalk Server 组添加到的计算机，单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**.</span><span class="sxs-lookup"><span data-stu-id="90177-113">On the computer that you want to add to a BizTalk Server group to, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="90177-114">在**Microsoft BizTalk Server 配置**，选择**自定义配置**。</span><span class="sxs-lookup"><span data-stu-id="90177-114">In **Microsoft BizTalk Server Configuration**, select **Custom configuration**.</span></span>  
  
3.  <span data-ttu-id="90177-115">在**数据库服务器名称**，服务器将加入 BizTalk 组键入 SQL Server 的名称。</span><span class="sxs-lookup"><span data-stu-id="90177-115">In **Database server name**, type the name of the SQL Server for the BizTalk Group the server is joining.</span></span>  
  
4.  <span data-ttu-id="90177-116">在**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="90177-116">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="90177-117">在屏幕左侧的导航树中，单击**企业 SSO**。</span><span class="sxs-lookup"><span data-stu-id="90177-117">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  
  
6.  <span data-ttu-id="90177-118">上**企业单一登录**页上，单击**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="90177-118">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  
  
     <span data-ttu-id="90177-119">确保服务器名称和数据库名称均指向该服务器要添加到的 BizTalk Server 组的主 SSO 数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="90177-119">Ensure that the server name and database name point to the master SSO database server for the BizTalk Server group the server is joining.</span></span>  
  
7.  <span data-ttu-id="90177-120">在屏幕左侧的导航树中，单击**组**。</span><span class="sxs-lookup"><span data-stu-id="90177-120">In the navigation tree on the left side of the screen, click **Group**.</span></span>  
  
8.  <span data-ttu-id="90177-121">上**组**页上，单击**加入现有的 BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="90177-121">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  
  
     <span data-ttu-id="90177-122">确保服务器名称和数据库名称均指向该服务器要添加到的 BizTalk Server 组的数据库。</span><span class="sxs-lookup"><span data-stu-id="90177-122">Ensure that the server name and database name point to the databases for the BizTalk Server group the server is joining.</span></span>  
  
9. <span data-ttu-id="90177-123">在菜单栏中，单击**应用配置**若要在此计算机上配置企业单一登录和组。</span><span class="sxs-lookup"><span data-stu-id="90177-123">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the Group on this computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90177-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90177-124">See Also</span></span>  
 <span data-ttu-id="90177-125">[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md) </span><span class="sxs-lookup"><span data-stu-id="90177-125">[Working with the Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span></span>  
 <span data-ttu-id="90177-126">[管理组](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="90177-126">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="90177-127">[BizTalk 组](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="90177-127">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="90177-128">[如何将服务器从一个组移到另一个](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="90177-128">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 <span data-ttu-id="90177-129">[如何从组中删除服务器](../core/how-to-remove-a-server-from-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="90177-129">[How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md) </span></span>  
 <span data-ttu-id="90177-130">[如何修改组属性](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="90177-130">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 [<span data-ttu-id="90177-131">管理服务器</span><span class="sxs-lookup"><span data-stu-id="90177-131">Managing Servers</span></span>](../core/managing-servers.md)