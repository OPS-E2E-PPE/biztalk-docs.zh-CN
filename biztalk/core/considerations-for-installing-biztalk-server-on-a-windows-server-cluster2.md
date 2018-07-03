---
title: 在 Windows Server Cluster2 上安装 BizTalk Server 的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configure Your Server Wizard
- installing, Windows Server cluster
- BizTalk Server Configuration Wizard
- Windows Server cluster, warnings
- high availability, Windows Server cluster
- clustering, Windows Server cluster
- domain groups
- Windows Server cluster, Configure Your Server Wizard
- Network DTC access
- MSDTC
ms.assetid: 4daea7c6-7d26-440c-a2a0-fa018a25b2b3
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96902a81fdd61b7c7d10f9bb2fc275dd18d23b72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000790"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a><span data-ttu-id="5abbc-102">在 Windows Server 群集上安装 BizTalk Server 的注意事项</span><span class="sxs-lookup"><span data-stu-id="5abbc-102">Considerations for Installing BizTalk Server on a Windows Server Cluster</span></span>
<span data-ttu-id="5abbc-103">安装时必须考虑特殊注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server 群集上。</span><span class="sxs-lookup"><span data-stu-id="5abbc-103">Special considerations must be made when installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a Windows Server cluster.</span></span> <span data-ttu-id="5abbc-104">本主题中将列出这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="5abbc-104">This topic lists these considerations.</span></span>  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a><span data-ttu-id="5abbc-105">非群集 BizTalk 主机实例不应运行于群集了企业 SSO 服务的 Windows Server 群集上</span><span class="sxs-lookup"><span data-stu-id="5abbc-105">A non-clustered BizTalk host instance should not be run on a Windows Server cluster where the Enterprise SSO service is clustered</span></span>  
 <span data-ttu-id="5abbc-106">建议您以主动/被动配置对企业单一登录主密钥服务器进行群集，以便确保主密钥服务器高度可用。</span><span class="sxs-lookup"><span data-stu-id="5abbc-106">It is a recommended practice to cluster the Enterprise Single Sign-On Master Secret Server in an active/passive configuration to provide high availability for the master secret server.</span></span> <span data-ttu-id="5abbc-107">如果非群集 BizTalk 主机实例和企业 SSO 服务的群集实例在同一个群集节点上运行，则在将群集企业 SSO 服务移到群集中的其他节点时，BizTalk 主机实例将失败。</span><span class="sxs-lookup"><span data-stu-id="5abbc-107">If a non-clustered BizTalk host instance and a clustered instance of the Enterprise SSO service are running on the same cluster node, the BizTalk host instance will fail if the clustered Enterprise SSO service is moved to a different node in the cluster.</span></span> <span data-ttu-id="5abbc-108">BizTalk 主机对企业 SSO 服务的本地运行实例有依存关系。</span><span class="sxs-lookup"><span data-stu-id="5abbc-108">BizTalk Hosts maintain a dependency on a locally running instance of the Enterprise SSO service.</span></span> <span data-ttu-id="5abbc-109">因此如果企业 SSO 服务配置为群集资源，然后必须在群集节点上运行的任何 BizTalk 主机配置为在同一群集组中的群集资源中。</span><span class="sxs-lookup"><span data-stu-id="5abbc-109">Therefore if the Enterprise SSO service is configured as a clustered resource, then any BizTalk Hosts running on the cluster nodes must be configured as a clustered resource in the same cluster group.</span></span>  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a><span data-ttu-id="5abbc-110">在群集上安装 BizTalk Server 之前将 Microsoft 分布式事务处理协调器 (MSDTC) 配置为群集资源</span><span class="sxs-lookup"><span data-stu-id="5abbc-110">Configure the Microsoft Distributed Transaction Coordinator (MSDTC) as a clustered resource before installing BizTalk Server on a cluster</span></span>  
 <span data-ttu-id="5abbc-111">如果计划在 Windows Server 群集上安装 BizTalk Server，则必须首先对 Microsoft 分布式事务处理协调器进行群集。</span><span class="sxs-lookup"><span data-stu-id="5abbc-111">If you plan to install BizTalk Server on a Windows Server cluster, you must cluster the Microsoft Distributed Transaction Coordinator first.</span></span>  
  
 <span data-ttu-id="5abbc-112">若要在 Windows Server 2008 故障转移群集上对 MSDTC 进行群集，请按照中所述的步骤[核对清单： 在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/?LinkID=129677)</span><span class="sxs-lookup"><span data-stu-id="5abbc-112">To cluster MSDTC on a Windows Server 2008 failover cluster, follow the steps outlined in [Checklist: Creating an MS DTC Resource in a Windows Server 2008 Failover Cluster](http://go.microsoft.com/fwlink/?LinkID=129677)</span></span>  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a><span data-ttu-id="5abbc-113">必须在所有 BizTalk Server 和 SQL Server 上启用网络 DTC 访问，然后才能安装或配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="5abbc-113">Network DTC access must be enabled on all BizTalk Servers and on the SQL Server before installing or configuring BizTalk Server</span></span>  
 <span data-ttu-id="5abbc-114">若要启用网络 DTC 访问每个群集节点上以及在将承载 BizTalk Server 数据库的 SQL 服务器上，请按照中所述的步骤[如何在 Web 服务器上启用 MSDTC](http://go.microsoft.com/fwlink/?LinkId=189701) (<http://go.microsoft.com/fwlink/?LinkId=189701>)。</span><span class="sxs-lookup"><span data-stu-id="5abbc-114">To enable network DTC access on each cluster node as well as on the SQL Server that will host the BizTalk Server databases, follow the steps outlined in [How to Enable MSDTC on a Web Server](http://go.microsoft.com/fwlink/?LinkId=189701) (<http://go.microsoft.com/fwlink/?LinkId=189701>).</span></span> <span data-ttu-id="5abbc-115">必须启用网络 DTC 访问才能提供事务性支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5abbc-115">Network DTC access must be enabled to accommodate transactional support for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5abbc-116">建议您在完成此知识库文章中的步骤后，重新启动每台服务器。</span><span class="sxs-lookup"><span data-stu-id="5abbc-116">We recommend that you restart each server after completing the steps in this Knowledge Base article.</span></span>  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a><span data-ttu-id="5abbc-117">配置 BizTalk Server 前必须在 Active Directory 中手动创建域组</span><span class="sxs-lookup"><span data-stu-id="5abbc-117">You must manually create domain groups in Active Directory before you configure BizTalk Server</span></span>  
 <span data-ttu-id="5abbc-118">如果在多台计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导中指定域组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5abbc-118">If you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on multiple computers, you must specify domain groups and user accounts in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="5abbc-119">如果您将域组用于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置，则配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之前必须先手动创建这些组。</span><span class="sxs-lookup"><span data-stu-id="5abbc-119">If you use domain groups for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration, you must manually create the groups before you configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>