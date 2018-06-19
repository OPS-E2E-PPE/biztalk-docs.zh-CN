---
title: 管理员 （BizTalk Server 示例文件夹中） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK examples
- examples, administering
- administering, examples
ms.assetid: 178d0ee2-d437-4945-a35d-1a8be524aff1
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d50da9489338ff9b3bf00dd829d7001b12d1b93c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230989"
---
# <a name="admin-biztalk-server-samples-folder"></a><span data-ttu-id="ec1cb-102">Admin（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="ec1cb-102">Admin (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="ec1cb-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在其软件开发工具包 (SDK) 中包括了几个管理示例。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several administration samples in its software development kit (SDK).</span></span> <span data-ttu-id="ec1cb-104">本部分提供每个管理示例所演示功能的详细信息、生成和运行每个示例的说明以及预期得到的结果。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-104">This section provides detailed information about the functionality demonstrated by each administration sample, instructions for building and running the sample, and the results you can expect.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ec1cb-105">部署后，如果不再需要部署脚本，则应将其删除。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-105">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="ec1cb-106">应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-106">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec1cb-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ec1cb-107">In This Section</span></span>  
  
-   <span data-ttu-id="ec1cb-108">[管理员-ExplorerOM （BizTalk Server 示例文件夹中）](../core/admin-explorerom-biztalk-server-samples-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-108">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md).</span></span>  
  
    -   <span data-ttu-id="ec1cb-109">[ApplicationManager （BizTalk Server 示例）](../core/applicationmanager-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-109">[ApplicationManager (BizTalk Server Sample)](../core/applicationmanager-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-110">演示如何启动或停止 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-110">Demonstrates how to start or stop a BizTalk application.</span></span>  
  
    -   <span data-ttu-id="ec1cb-111">[BrowsingArtifacts （BizTalk Server 示例）](../core/browsingartifacts-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-111">[BrowsingArtifacts (BizTalk Server Sample)](../core/browsingartifacts-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-112">演示如何枚举 BizTalk 项目和属性。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-112">Demonstrates how to enumerate BizTalk artifacts and attributes.</span></span>  
  
    -   <span data-ttu-id="ec1cb-113">[CBR （BizTalk Server 示例）](../core/cbr-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-113">[CBR (BizTalk Server Sample)](../core/cbr-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-114">演示如何添加和配置新的基于内容的路由的 BizTalk 消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-114">Demonstrates adding and configuring new send ports for content based routing of BizTalk messages.</span></span>  
  
    -   <span data-ttu-id="ec1cb-115">[DeleteParty （BizTalk Server 示例）](../core/deleteparty-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-115">[DeleteParty (BizTalk Server Sample)](../core/deleteparty-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-116">演示如何删除指定的参与方。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-116">Demonstrates how to delete a specified party.</span></span>  
  
    -   <span data-ttu-id="ec1cb-117">[OrchestrationBinding （BizTalk Server 示例）](../core/orchestrationbinding-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-117">[OrchestrationBinding (BizTalk Server Sample)](../core/orchestrationbinding-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-118">演示如何管理和配置业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-118">Demonstrates how to manage and configure orchestrations.</span></span>  
  
    -   <span data-ttu-id="ec1cb-119">[PartnerManagement （BizTalk Server 示例）](../core/partnermanagement-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-119">[PartnerManagement (BizTalk Server Sample)](../core/partnermanagement-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-120">演示如何创建和删除的参与方。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-120">Demonstrates creating and deleting parties.</span></span> <span data-ttu-id="ec1cb-121">此外还演示如何用角色登记和解除登记参与方。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-121">Also demonstrates enlisting and unenlisting parties with roles.</span></span>  
  
    -   <span data-ttu-id="ec1cb-122">[接收位置 （BizTalk Server 示例）](../core/receivelocations-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-122">[ReceiveLocations (BizTalk Server Sample)](../core/receivelocations-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-123">演示如何创建和管理的接收端口接收位置。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-123">Demonstrates how to create and manage receive locations for receive ports.</span></span>  
  
    -   <span data-ttu-id="ec1cb-124">[接收端口 （BizTalk Server 示例）](../core/receiveports-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-124">[ReceivePorts (BizTalk Server Sample)](../core/receiveports-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-125">演示如何创建、 枚举和删除接收端口。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-125">Demonstrates creating, enumerating and deleting receive ports.</span></span>  
  
    -   <span data-ttu-id="ec1cb-126">[发送端口组 （BizTalk Server 示例）](../core/sendportgroups-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-126">[SendPortGroups (BizTalk Server Sample)](../core/sendportgroups-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-127">演示如何枚举和管理发送端口组。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-127">Demonstrates how to enumerate and manage send port groups.</span></span>  
  
    -   <span data-ttu-id="ec1cb-128">[发送端口 （BizTalk Server 示例）](../core/sendports-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-128">[SendPorts (BizTalk Server Sample)](../core/sendports-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-129">演示如何枚举和管理发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-129">Demonstrates how to enumerate and manage send ports.</span></span>  
  
    -   <span data-ttu-id="ec1cb-130">[UnenlistParties （BizTalk Server 示例）](../core/unenlistparties-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-130">[UnenlistParties (BizTalk Server Sample)](../core/unenlistparties-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-131">演示如何取消登记与部署的 BizTalk 程序集关联的所有参与方。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-131">Demonstrates how to unenlist all of the parties associated with a deployed BizTalk assembly.</span></span>  
  
    -   <span data-ttu-id="ec1cb-132">[Sysprep BizTalk Server VHD （BizTalk Server 示例）](../core/sysprep-a-biztalk-server-vhd-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-132">[Sysprep a BizTalk Server VHD (BizTalk Server Sample)](../core/sysprep-a-biztalk-server-vhd-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-133">演示如何操作 Sysprep 将创建具有的虚拟机的快照[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]快速部署其他虚拟机上安装。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-133">Demonstrates how Sysprep creates a snapshot of a virtual machine with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installed for quick deployment on other virtual machines.</span></span>  
  
-   [<span data-ttu-id="ec1cb-134">管理员-OperationsOM （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="ec1cb-134">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)  
  
    -   [<span data-ttu-id="ec1cb-135">OperationsSamples （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ec1cb-135">OperationsSamples (BizTalk Server Sample)</span></span>](../core/operationssamples-biztalk-server-sample.md)  
  
-   [<span data-ttu-id="ec1cb-136">管理员-WMI （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="ec1cb-136">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)  
  
    -   <span data-ttu-id="ec1cb-137">[启用接收位置 （BizTalk Server 示例）](../core/enable-receive-location-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-137">[Enable Receive Location (BizTalk Server Sample)](../core/enable-receive-location-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-138">演示如何启用某接收位置和为此接受位置设置入站传输 URL。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-138">Demonstrates how to enable a receive location and set the Inbound Transport URL for that receive location.</span></span>  
  
    -   <span data-ttu-id="ec1cb-139">[登记业务流程 （BizTalk Server 示例）](../core/enlist-orchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-139">[Enlist Orchestration (BizTalk Server Sample)](../core/enlist-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-140">演示如何向主机登记 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-140">Demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
    -   <span data-ttu-id="ec1cb-141">[枚举接收位置 （BizTalk Server 示例）](../core/enumerate-receive-locations-biztalk-server-sample.md)示例。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-141">[Enumerate Receive Locations (BizTalk Server Sample)](../core/enumerate-receive-locations-biztalk-server-sample.md) Sample.</span></span> <span data-ttu-id="ec1cb-142">演示如何检索有关一个或多个接收位置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-142">Demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
    -   <span data-ttu-id="ec1cb-143">[删除接收端口 （BizTalk Server 示例）](../core/remove-receive-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-143">[Remove Receive Port (BizTalk Server Sample)](../core/remove-receive-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-144">演示如何删除一个或多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-144">Demonstrates how to remove one or more receive ports.</span></span>  
  
    -   <span data-ttu-id="ec1cb-145">[删除发送端口 （BizTalk Server 示例）](../core/remove-send-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-145">[Remove Send Port (BizTalk Server Sample)](../core/remove-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-146">演示如何取消登记和删除一个或多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-146">Demonstrates how to unenlist and remove one or more send ports.</span></span>  
  
    -   <span data-ttu-id="ec1cb-147">[设置发送处理程序属性 （BizTalk Server 示例）](../core/set-send-handler-property-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-147">[Set Send Handler Property (BizTalk Server Sample)](../core/set-send-handler-property-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-148">演示如何为简单邮件传输协议 (SMTP) 发送处理程序设置 XML 配置信息。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-148">Demonstrates how to set the XML configuration information for a Simple Mail Transfer Protocol (SMTP) send handler.</span></span>  
  
    -   <span data-ttu-id="ec1cb-149">[开始发送端口 （BizTalk Server 示例）](../core/start-send-port-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-149">[Start Send Port (BizTalk Server Sample)](../core/start-send-port-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-150">演示如何在使用 FILE 适配器时启动发送端口和设置主传输地址。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-150">Demonstrates how to start a send port and set the Primary Transport Address when using the FILE adapter.</span></span>  
  
    -   <span data-ttu-id="ec1cb-151">[停止业务流程 （BizTalk Server 示例）](../core/stop-orchestration-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-151">[Stop Orchestration (BizTalk Server Sample)](../core/stop-orchestration-biztalk-server-sample.md).</span></span> <span data-ttu-id="ec1cb-152">演示如何停止 BizTalk Server 业务流程和对其取消登记，后者可选。</span><span class="sxs-lookup"><span data-stu-id="ec1cb-152">Demonstrates how to stop a BizTalk Server orchestration and, optionally, to unenlist it.</span></span>