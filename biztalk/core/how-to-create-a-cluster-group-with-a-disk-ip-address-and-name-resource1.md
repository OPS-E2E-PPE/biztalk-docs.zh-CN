---
title: 如何使用磁盘，IP 地址，创建群集组，并命名 Resource1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63310706742ffcc10de5266dda7053da79fc04fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249301"
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a><span data-ttu-id="2ac5c-102">如何创建具有磁盘、IP 地址和名称资源的群集组</span><span class="sxs-lookup"><span data-stu-id="2ac5c-102">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>
<span data-ttu-id="2ac5c-103">为群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件和依赖项以通过 NetBIOS，群集通过网络来访问它**网络名称**必须在相同的群集组中创建资源。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-103">For clustered [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components and dependencies to be accessible over the network via NetBIOS, a clustered **Network Name** resource must be created in same cluster group.</span></span> <span data-ttu-id="2ac5c-104">对于群集的网络名称资源，可通过 TCP/IP 协议， **IP 地址**必须在相同的群集组中创建资源。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-104">For a clustered Network Name resource to be accessible via the TCP/IP protocol, an **IP Address** resource must be created in the same cluster group as well.</span></span> <span data-ttu-id="2ac5c-105">某些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖关系还需要使用聚集**物理磁盘**资源才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-105">Some [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] dependencies also require the use of a clustered **Physical Disk** resource to function correctly.</span></span> <span data-ttu-id="2ac5c-106">若要创建的群集组**物理磁盘**， **IP 地址**和**网络名称**资源，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="2ac5c-106">To create a cluster group with a **Physical Disk**, **IP Address** and **Network Name** resource follow these steps:</span></span>  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a><span data-ttu-id="2ac5c-107">创建具有物理磁盘、IP 地址和网络名称资源的服务或应用程序</span><span class="sxs-lookup"><span data-stu-id="2ac5c-107">To create a service or application with a Physical Disk, IP Address, and Network Name resource</span></span>  
  
1.  <span data-ttu-id="2ac5c-108">在 Windows 中，单击**启动**，**程序**，**管理工具**，，然后**故障转移群集管理**启动故障转移群集管理程序。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-108">In Windows, click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
2.  <span data-ttu-id="2ac5c-109">将所有服务和应用程序故障转移到运行故障转移群集管理的群集节点上。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-109">Fail over all services and applications to the cluster node that you are running Failover Cluster Management on.</span></span> <span data-ttu-id="2ac5c-110">若要故障转移服务或应用程序，右键单击该服务或应用程序的左窗格中的故障转移群集管理、 指向**将此服务或应用程序到另一个节点移动**和单击此项可选择的目标节点。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-110">To fail over a service or application, right click the service or application in the left pane of Failover Cluster Management, point to **Move this service or application to another node** and click to select the destination node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ac5c-111">承载正在运行的群集资源的群集节点是也称为**active**节点。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-111">The cluster node that hosts running cluster resources is also known as the **active** node.</span></span> <span data-ttu-id="2ac5c-112">承载非运行群集资源的群集节点是也称为**被动**节点。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-112">The cluster node that hosts non-running cluster resources is also known as the **passive** node.</span></span>  
  
3.  <span data-ttu-id="2ac5c-113">在左侧窗格中，右键单击**服务和应用程序**，单击**配置服务或应用程序**以启动高可用性向导，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="2ac5c-113">In the left-hand pane, right-click **Services and Applications**, click **Configure a Service or Application** to launch the High Availability Wizard, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2ac5c-114">单击以选择**文件服务器**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-114">Click to select **File Server** and click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ac5c-115">选择**文件服务器**此时都将作为与磁盘资源创建的群集组的简单方法。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-115">Selecting **File Server** at this point is done as a straightforward way to create a cluster group with a disk resource.</span></span>  
  
5.  <span data-ttu-id="2ac5c-116">上**客户端访问点**的高可用性向导页上，输入唯一的网络名称**名称**框中，例如*BizTalkCluster*，输入一个可用的 IP在地址**地址**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-116">On the **Client Access Point** page of the High Availability Wizard enter a unique network name into the **Name** box, for example *BizTalkCluster*, enter an available IP address under **Address**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="2ac5c-117">上**选择存储**页上，单击此项可选择可用磁盘资源，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-117">On the **Select Storage** page, click to select an available disk resource and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="2ac5c-118">上**确认**页上，单击**下一步**若要创建的群集组。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-118">On the **Confirmation** page click **Next** to create the cluster group.</span></span>  
  
8.  <span data-ttu-id="2ac5c-119">上**摘要**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="2ac5c-119">On the **Summary** page click **Finish**.</span></span>