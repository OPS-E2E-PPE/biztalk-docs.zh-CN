---
title: "管理员-ExplorerOM （BizTalk Server 示例文件夹中） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, administering
- administering, examples
ms.assetid: f6553138-9ab3-4368-84bf-9813e909e372
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b8b33db0460a5e44ecfcd732535022bb28940d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="admin-explorerom-biztalk-server-samples-folder"></a><span data-ttu-id="0a25e-102">管理员-ExplorerOM （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="0a25e-102">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="0a25e-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括在其软件开发工具包 (SDK) 的 Admin\ExplorerOM 文件夹中的示例。</span><span class="sxs-lookup"><span data-stu-id="0a25e-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes samples in the Admin\ExplorerOM folder in its software development kit (SDK).</span></span> <span data-ttu-id="0a25e-104">本部分详细介绍了每个 BizTalk 浏览器对象模型管理示例所演示的功能、生成和运行每个示例的说明以及可以预期得到的结果。</span><span class="sxs-lookup"><span data-stu-id="0a25e-104">This section provides detailed information about the functionality demonstrated by each BizTalk Explorer object model administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="0a25e-105">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="0a25e-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="0a25e-106">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="0a25e-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a25e-107">Microsoft.BizTalk.ExplorerOM.dll 支持 32 位和 64 位进程。</span><span class="sxs-lookup"><span data-stu-id="0a25e-107">Microsoft.BizTalk.ExplorerOM.dll supports both 32 bit and 64 bit processes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a25e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="0a25e-108">In This Section</span></span>  
  
-   <span data-ttu-id="0a25e-109">[ApplicationManager （BizTalk Server 示例）](../core/applicationmanager-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-109">[ApplicationManager (BizTalk Server Sample)](../core/applicationmanager-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-110">演示如何启动或停止 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a25e-110">Demonstrates how to start or stop a BizTalk application.</span></span>  
  
-   <span data-ttu-id="0a25e-111">[BrowsingArtifacts （BizTalk Server 示例）](../core/browsingartifacts-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-111">[BrowsingArtifacts (BizTalk Server Sample)](../core/browsingartifacts-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-112">演示如何枚举 BizTalk 项目和属性。</span><span class="sxs-lookup"><span data-stu-id="0a25e-112">Demonstrates how to enumerate BizTalk artifacts and attributes.</span></span>  
  
-   <span data-ttu-id="0a25e-113">[CBR （BizTalk Server 示例）](../core/cbr-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-113">[CBR (BizTalk Server Sample)](../core/cbr-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-114">演示如何添加和配置新的基于内容的路由的 BizTalk 消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="0a25e-114">Demonstrates adding and configuring new send ports for content based routing of BizTalk messages.</span></span>  
  
-   <span data-ttu-id="0a25e-115">[DeleteParty （BizTalk Server 示例）](../core/deleteparty-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-115">[DeleteParty (BizTalk Server Sample)](../core/deleteparty-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-116">演示如何删除指定的参与方。</span><span class="sxs-lookup"><span data-stu-id="0a25e-116">Demonstrates how to delete a specified party.</span></span>  
  
-   <span data-ttu-id="0a25e-117">[OrchestrationBinding （BizTalk Server 示例）](../core/orchestrationbinding-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-117">[OrchestrationBinding (BizTalk Server Sample)](../core/orchestrationbinding-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-118">演示如何配置和管理业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a25e-118">Demonstrates configuring and managing orchestrations.</span></span>  
  
-   <span data-ttu-id="0a25e-119">[PartnerManagement （BizTalk Server 示例）](../core/partnermanagement-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-119">[PartnerManagement (BizTalk Server Sample)](../core/partnermanagement-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-120">演示如何创建和删除的参与方。</span><span class="sxs-lookup"><span data-stu-id="0a25e-120">Demonstrates creating and deleting parties.</span></span> <span data-ttu-id="0a25e-121">此外还演示登记和取消登记具有角色的参与方。</span><span class="sxs-lookup"><span data-stu-id="0a25e-121">Also demonstrates enlisting and un-enlisting parties with roles.</span></span>  
  
-   <span data-ttu-id="0a25e-122">[接收位置 （BizTalk Server 示例）](../core/receivelocations-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-122">[ReceiveLocations (BizTalk Server Sample)](../core/receivelocations-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-123">演示如何创建和管理的接收端口接收位置。</span><span class="sxs-lookup"><span data-stu-id="0a25e-123">Demonstrates how to create and manage receive locations for receive ports.</span></span>  
  
-   <span data-ttu-id="0a25e-124">[接收端口 （BizTalk Server 示例）](../core/receiveports-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-124">[ReceivePorts (BizTalk Server Sample)](../core/receiveports-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-125">演示如何创建、 枚举和删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="0a25e-125">Demonstrates creating, enumerating and deleting receive ports.</span></span>  
  
-   <span data-ttu-id="0a25e-126">[发送端口组 （BizTalk Server 示例）](../core/sendportgroups-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-126">[SendPortGroups (BizTalk Server Sample)](../core/sendportgroups-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-127">演示如何枚举和管理发送端口组。</span><span class="sxs-lookup"><span data-stu-id="0a25e-127">Demonstrates how to enumerate and manage send port groups.</span></span>  
  
-   <span data-ttu-id="0a25e-128">[发送端口 （BizTalk Server 示例）](../core/sendports-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-128">[SendPorts (BizTalk Server Sample)](../core/sendports-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-129">演示如何枚举和管理发送端口。</span><span class="sxs-lookup"><span data-stu-id="0a25e-129">Demonstrates how to enumerate and manage send ports.</span></span>  
  
-   <span data-ttu-id="0a25e-130">[UnenlistParties （BizTalk Server 示例）](../core/unenlistparties-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25e-130">[UnenlistParties (BizTalk Server Sample)](../core/unenlistparties-biztalk-server-sample.md).</span></span> <span data-ttu-id="0a25e-131">演示如何取消登记与部署的 BizTalk 程序集关联的所有参与方。</span><span class="sxs-lookup"><span data-stu-id="0a25e-131">Demonstrates how to unenlist all of the parties associated with a deployed BizTalk assembly.</span></span>