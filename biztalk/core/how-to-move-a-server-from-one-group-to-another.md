---
title: "如何将服务器从一个组移到另一个 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- groups, servers
- groups, moving
- managing [groups], moving servers
- servers, moving
- managing [servers], moving
- servers, groups
ms.assetid: 3f789a62-f597-426b-9cea-74c1fe22b694
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9e5dfdf266d2205283afa7cd9804c31fc93ff3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a><span data-ttu-id="84c2e-102">如何将服务器从一个组移到另一个</span><span class="sxs-lookup"><span data-stu-id="84c2e-102">How to Move a Server from One Group to Another</span></span>
<span data-ttu-id="84c2e-103">一台服务器只能与一个 BizTalk Server 组相关联。</span><span class="sxs-lookup"><span data-stu-id="84c2e-103">A server can only be associated with one BizTalk Server group.</span></span> <span data-ttu-id="84c2e-104">若要将服务器从一个组移至另一个组，则必须首先通过取消原始组中对该服务器的配置将其从组中删除，然后再将该服务器添加到新组中。</span><span class="sxs-lookup"><span data-stu-id="84c2e-104">To move a server from one group to another, you must first remove the server from the original group by unconfiguring it, and then add the server to the new group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84c2e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="84c2e-105">Prerequisites</span></span>  
 <span data-ttu-id="84c2e-106">若要执行此过程，必须以 SSO Administrators 组成员和 Windows Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="84c2e-106">To perform this procedure, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a><span data-ttu-id="84c2e-107">将服务器从一个 BizTalk 组移至另一个 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="84c2e-107">To move a server from one BizTalk group to another</span></span>  
  
1.  <span data-ttu-id="84c2e-108">在你想要从 BizTalk 组移到另一个计算机，单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**.</span><span class="sxs-lookup"><span data-stu-id="84c2e-108">On the computer that you want to move from the BizTalk group to another, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="84c2e-109">在菜单栏中，单击**取消配置功能**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-109">On the menu bar, click **Unconfigure Features**.</span></span>  
  
3.  <span data-ttu-id="84c2e-110">在**取消配置功能**对话框中，选择**企业 SSO**，选择**组**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-110">In the **Unconfigure Features** dialog box, select **Enterprise SSO**, select **Group**, and then click **OK**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="84c2e-111">取消组配置还将取消配置该计算机上已配置的所有依存功能。</span><span class="sxs-lookup"><span data-stu-id="84c2e-111">Unconfiguring a group will also unconfigure all dependent features that are already configured on that computer.</span></span>  
  
4.  <span data-ttu-id="84c2e-112">单击 **“是”**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-112">Click **Yes**.</span></span>  
  
5.  <span data-ttu-id="84c2e-113">在**Microsoft BizTalk Server 配置**窗口中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-113">In the **Microsoft BizTalk Server Configuration** window, click **Next**.</span></span>  
  
     <span data-ttu-id="84c2e-114">这样就取消了对企业 SSO、组及其依存功能的配置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-114">Enterprise SSO, the Group, and their dependent features are unconfigured.</span></span>  
  
6.  <span data-ttu-id="84c2e-115">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-115">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="84c2e-116">在**Microsoft BizTalk Server 配置**窗口中，选择**自定义配置**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-116">In the **Microsoft BizTalk Server Configuration** window, select **Custom configuration**.</span></span>  
  
8.  <span data-ttu-id="84c2e-117">在**数据库服务器名称**，其中将服务器转移 BizTalk 组键入 SQL server 的名称。</span><span class="sxs-lookup"><span data-stu-id="84c2e-117">In **Database server name**, type the name of the SQL server for the BizTalk Group where you are moving the server.</span></span>  
  
9. <span data-ttu-id="84c2e-118">在**服务凭据**，键入相应的用户名和密码，服务将使用，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-118">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="84c2e-119">在屏幕左侧的导航树中，单击**企业 SSO**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-119">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  
  
11. <span data-ttu-id="84c2e-120">上**企业单一登录**页上，单击**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-120">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  
  
     <span data-ttu-id="84c2e-121">确保服务器名称和数据库名称均指向该服务器要移动到的 BizTalk Server 组的主 SSO 数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="84c2e-121">Ensure that the server name and database name point to the master SSO database server for the BizTalk Server group where you are moving the server.</span></span>  
  
12. <span data-ttu-id="84c2e-122">在屏幕左侧的导航树中，单击**组**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-122">In the navigation tree on the left side of the screen, click **Group**.</span></span>  
  
13. <span data-ttu-id="84c2e-123">上**组**页上，单击**加入现有的 BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-123">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  
  
     <span data-ttu-id="84c2e-124">确保服务器名称和数据库名称均指向该服务器要移动到的 BizTalk Server 组的数据库。</span><span class="sxs-lookup"><span data-stu-id="84c2e-124">Ensure that the server name and database name point to the databases for the BizTalk Server group where you are moving the server.</span></span>  
  
14. <span data-ttu-id="84c2e-125">在菜单栏中，单击**应用配置**若要在此计算机上配置企业单一登录和组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-125">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the Group on this computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c2e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84c2e-126">See Also</span></span>  
 <span data-ttu-id="84c2e-127">[管理组](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-127">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="84c2e-128">[BizTalk 组](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-128">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="84c2e-129">[如何将服务器添加到组](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-129">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="84c2e-130">[如何从组中删除服务器](../core/how-to-remove-a-server-from-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-130">[How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md) </span></span>  
 <span data-ttu-id="84c2e-131">[如何修改组属性](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-131">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 <span data-ttu-id="84c2e-132">[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-132">[Working with the Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span></span>  
 <span data-ttu-id="84c2e-133">[如何添加的主机实例](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="84c2e-133">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 [<span data-ttu-id="84c2e-134">管理服务器</span><span class="sxs-lookup"><span data-stu-id="84c2e-134">Managing Servers</span></span>](../core/managing-servers.md)