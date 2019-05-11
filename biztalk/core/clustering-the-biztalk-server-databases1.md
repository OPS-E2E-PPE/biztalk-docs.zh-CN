---
title: 聚类分析 BizTalk Server Databases1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, how to
- clustering, SQL Servers
- SQL Server, clustering
- BizTalk Server Configuration Wizard
- high availability, databases
- clustering, BizTalk Server Configuration Wizard
- clustering, databases
- clustering, prerequisites
ms.assetid: 9a1ed843-483b-4a56-961b-bc6801a07b64
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a098e465178cd696249c483a17dd65c5d595c349
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528199"
---
# <a name="clustering-the-biztalk-server-databases"></a><span data-ttu-id="bdceb-102">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bdceb-102">Clustering the BizTalk Server Databases</span></span>
<span data-ttu-id="bdceb-103">此部分提供了部署 Microsoft 的指导原则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="bdceb-103">This section provides guidelines for deploying a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution with high availability.</span></span> <span data-ttu-id="bdceb-104">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库变得不可用，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="bdceb-104">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases become unavailable, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment will not function correctly.</span></span> <span data-ttu-id="bdceb-105">若要提供高可用性，可以创建的 Microsoft SQL Server 群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="bdceb-105">To provide high availability, you can create a Microsoft SQL Server cluster for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="bdceb-106">![BizTalk Server 数据库层](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span><span class="sxs-lookup"><span data-stu-id="bdceb-106">![BizTalk Server Database Tier](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")</span></span>  
  
 <span data-ttu-id="bdceb-107">若要提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，必须具有至少两台计算机正在运行的 SQL Server 和使用一个共享的磁盘阵列的 Windows Server 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="bdceb-107">To provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, you must have at least two computers that are running SQL Server and a shared disk array for use by a  Windows Server Failover Cluster.</span></span>  
  
## <a name="procedures-for-clustering-the-databases"></a><span data-ttu-id="bdceb-108">聚类分析数据库的过程</span><span class="sxs-lookup"><span data-stu-id="bdceb-108">Procedures for Clustering the Databases</span></span>  
  
#### <a name="before-you-start"></a><span data-ttu-id="bdceb-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="bdceb-109">Before you start</span></span>  
  
1. <span data-ttu-id="bdceb-110">BizTalk Server 环境中创建域组时，必须创建 Active Directory 域全局组。</span><span class="sxs-lookup"><span data-stu-id="bdceb-110">When you create the domain groups for your BizTalk Server environment, you must create Active Directory domain global groups.</span></span>  
  
2. <span data-ttu-id="bdceb-111">安装和配置之前配置 SQL Server 群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdceb-111">Configure the SQL Server cluster before you install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="bdceb-112">有关群集 SQL Server 的详细信息，请参阅[Alwayson 故障转移群集实例](https://technet.microsoft.com/library/ms189134.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bdceb-112">For more information about clustering SQL Server, see [Always On Failover Cluster Instances](https://technet.microsoft.com/library/ms189134.aspx).</span></span>  
  
3. <span data-ttu-id="bdceb-113">如果您要群集主密钥服务器，请首先配置该服务器。</span><span class="sxs-lookup"><span data-stu-id="bdceb-113">If you are also clustering the master secret server, configure that server first.</span></span> <span data-ttu-id="bdceb-114">企业单一登录的高可用性的详细信息，请参阅[为企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)。</span><span class="sxs-lookup"><span data-stu-id="bdceb-114">For more information about high availability for Enterprise Single Sign-On, see [High Availability for Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).</span></span>  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a><span data-ttu-id="bdceb-115">若要运行 BizTalk Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="bdceb-115">To run the BizTalk Server Configuration Wizard</span></span>  
  
1. <span data-ttu-id="bdceb-116">安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器上。</span><span class="sxs-lookup"><span data-stu-id="bdceb-116">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a runtime server.</span></span>  
  
2. <span data-ttu-id="bdceb-117">启动 BizTalk 配置程序。</span><span class="sxs-lookup"><span data-stu-id="bdceb-117">Launch the BizTalk Configuration Program.</span></span> <span data-ttu-id="bdceb-118">单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 配置**。</span><span class="sxs-lookup"><span data-stu-id="bdceb-118">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3. <span data-ttu-id="bdceb-119">按照中的步骤[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)应用自定义配置。</span><span class="sxs-lookup"><span data-stu-id="bdceb-119">Follow the steps in [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md) to apply a custom configuration.</span></span> <span data-ttu-id="bdceb-120">若要指定为 BizTalk 数据库的 SQL Server 群集，请输入中的 SQL Server 群集的名称**数据库**对话框中的配置程序中所述**编辑数据库**部分本主题中。</span><span class="sxs-lookup"><span data-stu-id="bdceb-120">To specify the SQL Server cluster for the BizTalk databases, enter the name of the SQL Server cluster in the **Databases** dialog of the configuration program as described in the **Editing Databases** section of this topic.</span></span>  
  
4. <span data-ttu-id="bdceb-121">按照中的说明完成 BizTalk Server 配置[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="bdceb-121">Complete the BizTalk Server configuration by following the instructions in [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdceb-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdceb-122">See Also</span></span>  
 [<span data-ttu-id="bdceb-123">创建高度可用的 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="bdceb-123">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)