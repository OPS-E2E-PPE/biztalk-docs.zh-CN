---
title: "管理 BizTalk 主机和主机实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [hosts]
- hosts, managing
- managing [hosts], about managing hosts
ms.assetid: 7f329804-ca44-4799-8a5d-38b3146d8e5e
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e60981f69bc3ff71bdd8581659f9cdd20f87467
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-biztalk-hosts-and-host-instances"></a><span data-ttu-id="5c830-102">管理 BizTalk 主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="5c830-102">Managing BizTalk Hosts and Host Instances</span></span>
<span data-ttu-id="5c830-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机是一个由零个或多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时进程组成的逻辑集合，您可以在其中部署诸如适配器处理程序、接收位置（包括管道）和业务流程等项。</span><span class="sxs-lookup"><span data-stu-id="5c830-103">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host is a logical set of zero or more [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time processes in which you deploy items such as adapter handlers, receive locations (including pipelines), and orchestrations.</span></span> <span data-ttu-id="5c830-104">有关主机的详细信息，请参阅[主机](../core/hosts.md)。</span><span class="sxs-lookup"><span data-stu-id="5c830-104">For more information about hosts, see [Hosts](../core/hosts.md).</span></span>  
  
 <span data-ttu-id="5c830-105">主机实例是消息处理、接收和传输发生的过程。</span><span class="sxs-lookup"><span data-stu-id="5c830-105">A host instance is the process where the message processing, receiving, and transmitting occurs.</span></span> <span data-ttu-id="5c830-106">运行每个服务器上安装一个主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有映射到该服务器的一个或多个主机。</span><span class="sxs-lookup"><span data-stu-id="5c830-106">You install a host instance on each server running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that has one or more hosts mapped to that server.</span></span> <span data-ttu-id="5c830-107">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="5c830-107">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="5c830-108">主机具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="5c830-108">Hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="5c830-109">主机是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对象的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="5c830-109">Hosts are the logical containers of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="5c830-110">每个服务器上只能存在特定主机的一个实例。</span><span class="sxs-lookup"><span data-stu-id="5c830-110">Only one instance of a specific host can exist on each server.</span></span>  
  
-   <span data-ttu-id="5c830-111">可以将一个主机映射到多个服务器。</span><span class="sxs-lookup"><span data-stu-id="5c830-111">You can map one host to multiple servers.</span></span>  
  
 <span data-ttu-id="5c830-112">主机实例具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="5c830-112">Host instances have the following characteristics:</span></span>  
  
-   <span data-ttu-id="5c830-113">主机实例是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 对象的物理容器。</span><span class="sxs-lookup"><span data-stu-id="5c830-113">Host instances are the physical containers of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="5c830-114">将服务器映射到主机时，即创建了一个主机实例。</span><span class="sxs-lookup"><span data-stu-id="5c830-114">You create a host instance when you map a server to a host.</span></span>  
  
-   <span data-ttu-id="5c830-115">在进行负载平衡或故障转移时，一个服务器上可以存在不同主机的多个主机实例。</span><span class="sxs-lookup"><span data-stu-id="5c830-115">Multiple host instances (of different hosts) can exist on a server when load balancing or for failover.</span></span>  
  
 <span data-ttu-id="5c830-116">下图显示了服务器、主机和主机实例之间的关系：</span><span class="sxs-lookup"><span data-stu-id="5c830-116">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
 <span data-ttu-id="5c830-117">![主机、 主机实例和服务器关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="5c830-117">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
<span data-ttu-id="5c830-118">主机、 主机实例和服务器之间的关系</span><span class="sxs-lookup"><span data-stu-id="5c830-118">Relationship between hosts, host instances, and servers</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c830-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="5c830-119">In This Section</span></span>  
  
-   [<span data-ttu-id="5c830-120">如何创建 BizTalk 服务器宿主环境</span><span class="sxs-lookup"><span data-stu-id="5c830-120">How to Create a BizTalk Server Hosting Environment</span></span>](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [<span data-ttu-id="5c830-121">如何创建新的主机</span><span class="sxs-lookup"><span data-stu-id="5c830-121">How to Create a New Host</span></span>](../core/how-to-create-a-new-host.md)  
  
-   [<span data-ttu-id="5c830-122">如何修改主机属性</span><span class="sxs-lookup"><span data-stu-id="5c830-122">How to Modify Host Properties</span></span>](../core/how-to-modify-host-properties.md)  
  
-   [<span data-ttu-id="5c830-123">如何删除主机</span><span class="sxs-lookup"><span data-stu-id="5c830-123">How to Delete a Host</span></span>](../core/how-to-delete-a-host.md)  
  
-   [<span data-ttu-id="5c830-124">如何添加的主机实例</span><span class="sxs-lookup"><span data-stu-id="5c830-124">How to Add a Host Instance</span></span>](../core/how-to-add-a-host-instance.md)  
  
-   [<span data-ttu-id="5c830-125">如何启动的主机实例</span><span class="sxs-lookup"><span data-stu-id="5c830-125">How to Start a Host Instance</span></span>](../core/how-to-start-a-host-instance.md)  
  
-   [<span data-ttu-id="5c830-126">如何停止主机实例</span><span class="sxs-lookup"><span data-stu-id="5c830-126">How to Stop a Host Instance</span></span>](../core/how-to-stop-a-host-instance.md)  
  
-   [<span data-ttu-id="5c830-127">如何删除主机实例</span><span class="sxs-lookup"><span data-stu-id="5c830-127">How to Delete a Host Instance</span></span>](../core/how-to-delete-a-host-instance.md)  
  
-   [<span data-ttu-id="5c830-128">如何修改主机实例属性</span><span class="sxs-lookup"><span data-stu-id="5c830-128">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)