---
title: "如何刷新资源 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [resources], refreshing
- refreshing resources
- resources, refreshing
ms.assetid: d6ff7c9d-8aaf-42a4-b1a3-00c05f6ac869
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bee05b9f137bbec92eccfa217084b66f1e5bf8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-refresh-a-resource"></a><span data-ttu-id="71ba9-102">如何刷新资源</span><span class="sxs-lookup"><span data-stu-id="71ba9-102">How to Refresh a Resource</span></span>
<span data-ttu-id="71ba9-103">本主题介绍如何使用 BizTalk Server 管理控制台来刷新资源项目。</span><span class="sxs-lookup"><span data-stu-id="71ba9-103">This topic describes how to use the BizTalk Server Administration console to refresh a resource artifact.</span></span> <span data-ttu-id="71ba9-104">一种方法是更新 BizTalk 管理数据库中的项目信息。</span><span class="sxs-lookup"><span data-stu-id="71ba9-104">This updates the artifact information in the BizTalk Management database.</span></span> <span data-ttu-id="71ba9-105">另一种方法执行此操作是通过将项目添加到应用程序使用 BTSTask [AddResource 命令](../core/addresource-command.md)使用覆盖选项。</span><span class="sxs-lookup"><span data-stu-id="71ba9-105">Another way to do this is by adding the artifact to the application using the BTSTask [AddResource Command](../core/addresource-command.md) with the overwrite option.</span></span>  
  
 <span data-ttu-id="71ba9-106">资源项目包含在应用程序的“资源”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="71ba9-106">Resource artifacts are contained in an application's Resources folder.</span></span> <span data-ttu-id="71ba9-107">如果对源文件进行了更改，并要用更新后的文件替换应用程序中的文件，则要刷新资源项目</span><span class="sxs-lookup"><span data-stu-id="71ba9-107">You might want to refresh a resource artifact if you make changes to the source file and want to replace the file in the application with the updated file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71ba9-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="71ba9-108">Prerequisites</span></span>  
 <span data-ttu-id="71ba9-109">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="71ba9-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="71ba9-110">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="71ba9-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-refresh-a-resource-artifact"></a><span data-ttu-id="71ba9-111">刷新资源项目</span><span class="sxs-lookup"><span data-stu-id="71ba9-111">To refresh a resource artifact</span></span>  
  
1.  <span data-ttu-id="71ba9-112">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="71ba9-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="71ba9-113">在控制台树中，展开**BizTalk Server 管理**，展开包含资源项目的 BizTalk 组若要刷新，，然后展开包含该项目的应用程序。</span><span class="sxs-lookup"><span data-stu-id="71ba9-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the resource artifact to refresh, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="71ba9-114">单击**资源**文件夹，右键单击该文件以刷新，，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="71ba9-114">Click the **Resources** folder, right-click the file to refresh, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="71ba9-115">在**修改资源**对话框中，选择要刷新的文件，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="71ba9-115">In the **Modify Resources** dialog box, select the file to refresh, and then click **Refresh**.</span></span>  
  
5.  <span data-ttu-id="71ba9-116">浏览到你想要替换当前的文件中，更新文件，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="71ba9-116">Browse to the updated file with which you want to replace the current file, and then click **OK**.</span></span>  
  
     <span data-ttu-id="71ba9-117">当前文件将替换为该已更新文件。</span><span class="sxs-lookup"><span data-stu-id="71ba9-117">The current file is replaced with the updated file.</span></span> <span data-ttu-id="71ba9-118">在添加、 配置、 设置显示在**选项**选项卡**修改资源**对话框中应用于刷新的文件。</span><span class="sxs-lookup"><span data-stu-id="71ba9-118">In addition, the configuration, settings displayed on the **Options** tab of the **Modify Resources** dialog box are applied to the refreshed file.</span></span> <span data-ttu-id="71ba9-119">有关更改这些设置的详细信息，请单击**帮助**在对话框中。</span><span class="sxs-lookup"><span data-stu-id="71ba9-119">For more information about changing these settings, click **Help** in the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ba9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71ba9-120">See Also</span></span>  
 <span data-ttu-id="71ba9-121">[管理前期和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="71ba9-121">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 <span data-ttu-id="71ba9-122">[管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="71ba9-122">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="71ba9-123">管理资源</span><span class="sxs-lookup"><span data-stu-id="71ba9-123">Managing Resources</span></span>](../core/managing-resources.md)