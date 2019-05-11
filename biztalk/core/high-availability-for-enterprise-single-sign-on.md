---
title: 企业单一登录的高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 2016-02-29
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, availability
- high availability, SSO
- Master Secret server, high availability
- SSO, high availability
ms.assetid: 6c631b5c-7147-4cc0-b58a-6749e83df9d3
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fd572db5425b86a422fd1cca574ba7aba2e4262
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387583"
---
# <a name="high-availability-for-enterprise-single-sign-on"></a><span data-ttu-id="ae505-102">企业单一登录的高可用性</span><span class="sxs-lookup"><span data-stu-id="ae505-102">High Availability for Enterprise Single Sign-On</span></span>
<span data-ttu-id="ae505-103">即使您不使用企业单一登录 (SSO) 功能来映射凭据和单一登录，SSO 是整个 Microsoft 的关键部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基础结构，因为 BizTalk Server 使用 SSO 帮助确保信息的安全接收位置。</span><span class="sxs-lookup"><span data-stu-id="ae505-103">Even if you do not use the Enterprise Single-Sign-On (SSO) functionality for mapping credentials and single sign-on, SSO is a critical part of the overall Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] infrastructure, because BizTalk Server uses SSO to help secure information for the receive locations.</span></span>  
  
 <span data-ttu-id="ae505-104">必须配置主密钥服务器为安装 SSO 服务的第一个计算机。</span><span class="sxs-lookup"><span data-stu-id="ae505-104">You must configure the first computer where you install the SSO service as the master secret server.</span></span> <span data-ttu-id="ae505-105">主密钥服务器是存储主密钥 （加密密钥） 的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="ae505-105">The master secret server is the SSO server that stores the master secret (encryption key).</span></span> <span data-ttu-id="ae505-106">主密钥是 SSO 系统用来加密和解密的数据将存储在 SSO 数据库中的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ae505-106">The master secret is the encryption key that the SSO system uses to encrypt and decrypt the data it stores in the SSO database.</span></span>  
  
 <span data-ttu-id="ae505-107">如果 SSO 服务器出现故障，并且如果有其他 BizTalk Server 计算机 （并因此 SSO 服务器） 运行相同的主机实例，与其他 SSO 服务器将继续其工作。</span><span class="sxs-lookup"><span data-stu-id="ae505-107">If an SSO server fails, and if you have other BizTalk Server computers (and therefore SSO servers) running the same host instance, the other SSO servers continue doing their work.</span></span> <span data-ttu-id="ae505-108">这意味着，在主密钥服务器仍函数工作正常，因此 BizTalk Server 处理继续进行。</span><span class="sxs-lookup"><span data-stu-id="ae505-108">This means that the master secret server still functions correctly, and therefore the BizTalk Server processing continues.</span></span>  
  
 <span data-ttu-id="ae505-109">如果主服务器发生故障，包括凭据解密失败前, 运行的所有运行时操作仍可正常都继续。</span><span class="sxs-lookup"><span data-stu-id="ae505-109">If the master secret server fails, all run-time operations that were running before it failed, including decryption of credentials, continue successfully.</span></span> <span data-ttu-id="ae505-110">但是，无法加密新的凭据。</span><span class="sxs-lookup"><span data-stu-id="ae505-110">However, you cannot encrypt new credentials.</span></span> <span data-ttu-id="ae505-111">因此，BizTalk Server 环境具有依赖项可用性的主密钥服务器，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="ae505-111">Therefore, the BizTalk Server environment has a dependency on the availability of the master secret server, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="ae505-112">![故障点](../core/media/tdi-highava-pointsfailure-mss.gif "TDI_HighAva_PointsFailure_MSS")</span><span class="sxs-lookup"><span data-stu-id="ae505-112">![Points of Failure](../core/media/tdi-highava-pointsfailure-mss.gif "TDI_HighAva_PointsFailure_MSS")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae505-113">如果主密钥服务器变得不可用，然后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机实例仍可以通过使用直到主密钥的内存中缓存的副本执行运行时操作：</span><span class="sxs-lookup"><span data-stu-id="ae505-113">If the master secret server becomes unavailable, then [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances can still perform run-time operations by using the in-memory cached copy of the master secret until:</span></span>  
> 
> - <span data-ttu-id="ae505-114">重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="ae505-114">The host instances are restarted.</span></span>  
>   -   <span data-ttu-id="ae505-115">重新启动运行 BizTalk 主机实例的计算机上的 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="ae505-115">The SSO service on the computer running the BizTalk host instances is restarted.</span></span>  
>   -   <span data-ttu-id="ae505-116">SSO 主密钥发生更改。</span><span class="sxs-lookup"><span data-stu-id="ae505-116">The SSO master secret is changed.</span></span>  
> 
>   <span data-ttu-id="ae505-117">如果在重新启动 SSO 服务，则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机或如果 SSO 主密钥已发生更改，将从内存中释放主密钥的缓存的副本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须能够联系主密钥服务器获取的另一个副本主密钥。</span><span class="sxs-lookup"><span data-stu-id="ae505-117">If the SSO service is restarted on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers or if the SSO master secret is changed, then the cached copy of the master secret is released from memory and the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must be able to contact the master secret server to obtain another copy of the master secret.</span></span> <span data-ttu-id="ae505-118">如果主密钥服务器不可用的出于加密目的而需要访问主密钥服务器的任何管理操作将失败。</span><span class="sxs-lookup"><span data-stu-id="ae505-118">If the master secret server is unavailable then any administrative operations that require access to the master secret server for purposes of encryption will fail.</span></span>  
  
## <a name="making-the-master-secret-server-available"></a><span data-ttu-id="ae505-119">提供对主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="ae505-119">Making the Master Secret Server Available</span></span>  
 <span data-ttu-id="ae505-120">有关可用的 SSO 系统中，并且因此 BizTalk Server 环境中，只要它生成备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="ae505-120">For availability of the SSO system, and therefore of the BizTalk Server environment, it is critical that you back up the master secret as soon as it is generated.</span></span> <span data-ttu-id="ae505-121">如果您丢失主密钥，则会丢失 SSO 系统将通过使用该主密钥加密的数据。</span><span class="sxs-lookup"><span data-stu-id="ae505-121">If you lose it, you lose the data that the SSO system encrypted by using that master secret.</span></span> <span data-ttu-id="ae505-122">有关备份主密钥的详细信息，请参阅[如何返回主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="ae505-122">For more information about backing up the master secret, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
 <span data-ttu-id="ae505-123">您可以进行主密钥服务器可通过两种方式：</span><span class="sxs-lookup"><span data-stu-id="ae505-123">You can make the master secret server available in two ways:</span></span>  
  
-   <span data-ttu-id="ae505-124">**可用，但不是高度可用。**</span><span class="sxs-lookup"><span data-stu-id="ae505-124">**Available, but not highly available.**</span></span> <span data-ttu-id="ae505-125">所有 SSO 服务器都具有主密钥缓存在内存中，并将继续运行时操作，即使主密钥服务器发生故障。</span><span class="sxs-lookup"><span data-stu-id="ae505-125">All the SSO servers have the master secret cached in memory, and run-time operations will continue even if the master secret server fails.</span></span> <span data-ttu-id="ae505-126">但是，您将不能更改端口的配置或 SSO 配置。</span><span class="sxs-lookup"><span data-stu-id="ae505-126">However, you will not be able to change the configuration of ports or the SSO configuration.</span></span> <span data-ttu-id="ae505-127">BizTalk Server 运行时将继续正常工作，但不能进行任何设计更改。</span><span class="sxs-lookup"><span data-stu-id="ae505-127">The BizTalk Server runtime will continue working without problems, but you cannot make any design changes.</span></span>  
  
     <span data-ttu-id="ae505-128">即使此配置不具有高可用性，可能会令人满意，在大多数情况下，与扩展接收、 发送和处理主机保持一致。</span><span class="sxs-lookup"><span data-stu-id="ae505-128">Even if this configuration is not highly available, it can be satisfactory for most scenarios and it is consistent with scaling out the receiving, sending, and processing hosts.</span></span>  
  
-   <span data-ttu-id="ae505-129">**高度可用。**</span><span class="sxs-lookup"><span data-stu-id="ae505-129">**Highly available.**</span></span> <span data-ttu-id="ae505-130">若要为主密钥服务器提供冗余，在单独的主密钥服务器群集上使用 Windows 群集或现有数据库群集上配置主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="ae505-130">To provide redundancy for the master secret server, use Windows Clustering on a separate master secret server cluster, or configure the master secret server on an existing database cluster.</span></span> <span data-ttu-id="ae505-131">主密钥服务器提供的服务不会占用很多资源，并通常不会影响数据库的功能或数据库群集上安装时的性能。</span><span class="sxs-lookup"><span data-stu-id="ae505-131">The services provided by the master secret server do not consume many resources, and typically do not affect database functionality or performance when installed on a database cluster.</span></span> <span data-ttu-id="ae505-132">下图显示了如何使在主密钥服务器高度可用。</span><span class="sxs-lookup"><span data-stu-id="ae505-132">The following figure shows how you can make the master secret server highly available.</span></span>  
  
     <span data-ttu-id="ae505-133">![高度可用的主密钥服务器](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")</span><span class="sxs-lookup"><span data-stu-id="ae505-133">![Highly Available Master Secret Server](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")</span></span>  
  
     <span data-ttu-id="ae505-134">虽然此配置是高度可用，但它需要额外的硬件资源。</span><span class="sxs-lookup"><span data-stu-id="ae505-134">While this configuration is highly available, it requires additional hardware resources.</span></span> <span data-ttu-id="ae505-135">有关高可用性 sso 安装选项的详细信息，请参阅[高可用性 SSO 安装选项](../core/high-availability-sso-installation-options.md)。</span><span class="sxs-lookup"><span data-stu-id="ae505-135">For more information about high availability installation options for SSO, see [High-Availability SSO Installation Options](../core/high-availability-sso-installation-options.md).</span></span> <span data-ttu-id="ae505-136">本部分包括有关配置为高度可用群集资源在 Windows Server 群集上的 SSO 主密钥服务器详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ae505-136">This section includes detailed information about configuring the SSO master secret server as a highly available cluster resource on a Windows Server cluster.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae505-137">若要减少高度可用的解决方案的硬件资源，您可以在 SQL Server 群集中添加为群集资源在主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="ae505-137">To reduce the hardware resources for a highly available solution, you can add the master secret server as a cluster resource in your SQL Server cluster.</span></span> <span data-ttu-id="ae505-138">不需要购买额外的 BizTalk Server 许可证，才能在另一台计算机上安装 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="ae505-138">You do not need to purchase additional BizTalk Server licenses to install the SSO service on another computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae505-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae505-139">See Also</span></span>  
 <span data-ttu-id="ae505-140">[聚类分析 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md) </span><span class="sxs-lookup"><span data-stu-id="ae505-140">[Clustering the BizTalk Server Databases](../core/clustering-the-biztalk-server-databases1.md) </span></span>  
 <span data-ttu-id="ae505-141">[创建高度可用的 BizTalk Server 环境](../core/creating-a-highly-available-biztalk-server-environment.md) </span><span class="sxs-lookup"><span data-stu-id="ae505-141">[Creating a Highly Available BizTalk Server Environment](../core/creating-a-highly-available-biztalk-server-environment.md) </span></span>  
 [<span data-ttu-id="ae505-142">如何群集主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="ae505-142">How to Cluster the Master Secret Server</span></span>](../core/how-to-cluster-the-master-secret-server1.md)