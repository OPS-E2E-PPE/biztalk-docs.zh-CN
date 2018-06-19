---
title: FTP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FTP adapters
ms.assetid: 878dc0b0-d1d8-405a-a697-654dd18ba08e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc72b5166f8971392b41f275338bde593d325af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246333"
---
# <a name="ftp-adapter"></a><span data-ttu-id="f09ff-102">FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="f09ff-102">FTP Adapter</span></span>
<span data-ttu-id="f09ff-103">FTP 适配器可在 FTP 服务器与 Microsoft BizTalk Server 之间交换数据，并可将存储在各种平台中的重要数据与业务流应用程序进行集成。</span><span class="sxs-lookup"><span data-stu-id="f09ff-103">The FTP adapter exchanges data between an FTP server and Microsoft BizTalk Server, and allows for the integration of vital data stored on a variety of platforms with line-of-business applications.</span></span> <span data-ttu-id="f09ff-104">该适配器可以连接到 FTP 服务器通过 SOCKS4 或 SOCKS5 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="f09ff-104">The adapter can connect to the FTP server via SOCKS4 or SOCKS5 proxy server.</span></span>  
  
 <span data-ttu-id="f09ff-105">FTP 适配器可将大量的文件从 FTP 服务器传输到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="f09ff-105">The FTP adapter can transfer a large number of files from an FTP server to BizTalk Server.</span></span> <span data-ttu-id="f09ff-106">它还可作为业务流程的一部分来传输文件。</span><span class="sxs-lookup"><span data-stu-id="f09ff-106">It can also transfer files as part of an orchestration.</span></span>  
  
 <span data-ttu-id="f09ff-107">FTP 适配器包含两个适配器-接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="f09ff-107">The FTP adapter consists of two adapters — a receive adapter and a send adapter.</span></span>  

<span data-ttu-id="f09ff-108">本部分将介绍 FTP 接收和发送适配器，以及有关安全性和最佳做法的信息。</span><span class="sxs-lookup"><span data-stu-id="f09ff-108">This section describes the FTP receive and send adapters, as well as security and best-practice information.</span></span>  
  
 ## <a name="receive-adapter"></a><span data-ttu-id="f09ff-109">接收适配器</span><span class="sxs-lookup"><span data-stu-id="f09ff-109">Receive adapter</span></span>  
  
 <span data-ttu-id="f09ff-110">使用 FTP 接收适配器，可以将数据从 FTP 服务器移至 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f09ff-110">The FTP receive adapter enables you to move data from an FTP server to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f09ff-111">主要功能包括：</span><span class="sxs-lookup"><span data-stu-id="f09ff-111">Key features include:</span></span>  
  
-   <span data-ttu-id="f09ff-112">根据需要从 FTP 服务器请求文件</span><span class="sxs-lookup"><span data-stu-id="f09ff-112">Pulling files from the FTP server on demand</span></span>  
  
-   <span data-ttu-id="f09ff-113">根据可配置计划运行轮询</span><span class="sxs-lookup"><span data-stu-id="f09ff-113">Running polls based on a configurable schedule</span></span>  
  
-   <span data-ttu-id="f09ff-114">对 FTP 服务器进行轮询并直接将数据发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f09ff-114">Polling the FTP server and sending data directly to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="f09ff-115">指定 FTP 服务器作为 IP 地址、端口、密码和主机名称</span><span class="sxs-lookup"><span data-stu-id="f09ff-115">Specifying the FTP server as an IP address, port, password, and host name</span></span>  
  
-   <span data-ttu-id="f09ff-116">确保文件送达</span><span class="sxs-lookup"><span data-stu-id="f09ff-116">Guaranteed file delivery</span></span>  
  
     <span data-ttu-id="f09ff-117">FTP 接收适配器还可与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台和 BizTalk 浏览器一起使用以配置和管理每个接收函数，这些接收函数由以下配置项组成：</span><span class="sxs-lookup"><span data-stu-id="f09ff-117">The FTP receive adapter also works with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and BizTalk Explorer to configure and administer each receive function, which is composed of the following configuration items:</span></span>  
  
-   <span data-ttu-id="f09ff-118">运行 FTP 命令的轮询间隔（例如，60 分钟）</span><span class="sxs-lookup"><span data-stu-id="f09ff-118">Poll interval to run an FTP command (for example, 60 minutes)</span></span>  
  
-   <span data-ttu-id="f09ff-119">用于将文档路由到特定 BizTalk 发送端口或接收位置的信息</span><span class="sxs-lookup"><span data-stu-id="f09ff-119">Information with which to route the document to a specific BizTalk send port or receive location</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f09ff-120">FTP 接收适配器不支持从已分区的数据集中接收文件。</span><span class="sxs-lookup"><span data-stu-id="f09ff-120">The FTP receive adapter does not support receiving files from a partitioned data set.</span></span>  
  
## <a name="send-adapter"></a><span data-ttu-id="f09ff-121">发送适配器</span><span class="sxs-lookup"><span data-stu-id="f09ff-121">Send adapter</span></span>  
  
 <span data-ttu-id="f09ff-122">使用 FTP 发送适配器，可以将数据从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 移至 FTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="f09ff-122">The FTP send adapter enables you to move data from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to an FTP server.</span></span> <span data-ttu-id="f09ff-123">主要功能包括：</span><span class="sxs-lookup"><span data-stu-id="f09ff-123">Key features include:</span></span>  
  
-   <span data-ttu-id="f09ff-124">能够按需发送</span><span class="sxs-lookup"><span data-stu-id="f09ff-124">Ability to run sends on demand</span></span>  
  
-   <span data-ttu-id="f09ff-125">确保送达</span><span class="sxs-lookup"><span data-stu-id="f09ff-125">Guaranteed delivery</span></span>  
  
## <a name="supported-platforms"></a><span data-ttu-id="f09ff-126">支持的平台</span><span class="sxs-lookup"><span data-stu-id="f09ff-126">Supported platforms</span></span>  
<span data-ttu-id="f09ff-127">访问 FTP 服务器上的任何以下平台上存储的信息：</span><span class="sxs-lookup"><span data-stu-id="f09ff-127">Access information stored in an FTP server on any of the following platforms:</span></span>  

- [!INCLUDE[btsWinSvrNoVersion_md](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="f09ff-128"> 2016</span><span class="sxs-lookup"><span data-stu-id="f09ff-128"> 2016</span></span>

- [!INCLUDE[btsWinSrv2k12_md](../includes/btswinsrv2k12-md.md)]<span data-ttu-id="f09ff-129"> R2</span><span class="sxs-lookup"><span data-stu-id="f09ff-129"> R2</span></span>
  
-   [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]  
  
-   [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="f09ff-130"> 2008</span><span class="sxs-lookup"><span data-stu-id="f09ff-130"> 2008</span></span>  
  
-   [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]  
  
-   [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]<span data-ttu-id="f09ff-131"> 2000 Service Pack 3 (SP3) 和更高版本</span><span class="sxs-lookup"><span data-stu-id="f09ff-131"> 2000 Service Pack 3 (SP3) and later</span></span>  
  
-   <span data-ttu-id="f09ff-132">Sun Solaris 9.0</span><span class="sxs-lookup"><span data-stu-id="f09ff-132">Sun Solaris 9.0</span></span>  
  
-   <span data-ttu-id="f09ff-133">HP-UX</span><span class="sxs-lookup"><span data-stu-id="f09ff-133">HP-UX</span></span>  
  
-   <span data-ttu-id="f09ff-134">LINUX (Redhat 7.x)</span><span class="sxs-lookup"><span data-stu-id="f09ff-134">LINUX (Redhat 7.x)</span></span>  
  
-   <span data-ttu-id="f09ff-135">IBM z/OS v1.9 (MVS)</span><span class="sxs-lookup"><span data-stu-id="f09ff-135">IBM z/OS v1.9 (MVS)</span></span>  
  
-   <span data-ttu-id="f09ff-136">运行 MVS 的 IBM O/S 390</span><span class="sxs-lookup"><span data-stu-id="f09ff-136">IBM O/S 390 running MVS</span></span>  
  
-   <span data-ttu-id="f09ff-137">AS/400 OS/400 V5R1</span><span class="sxs-lookup"><span data-stu-id="f09ff-137">AS/400 OS/400 V5R1</span></span>  
  
-   <span data-ttu-id="f09ff-138">i5/OS V5R4 (AS400)</span><span class="sxs-lookup"><span data-stu-id="f09ff-138">i5/OS V5R4 (AS400)</span></span>  
  
-   <span data-ttu-id="f09ff-139">i5/OS V6R1 (AS400)</span><span class="sxs-lookup"><span data-stu-id="f09ff-139">i5/OS V6R1 (AS400)</span></span>  
  
-   <span data-ttu-id="f09ff-140">GXS ICS</span><span class="sxs-lookup"><span data-stu-id="f09ff-140">GXS ICS</span></span>  
  
-   <span data-ttu-id="f09ff-141">AIX</span><span class="sxs-lookup"><span data-stu-id="f09ff-141">AIX</span></span>  
  
 <span data-ttu-id="f09ff-142">支持所有服务包，专门列出的服务包除外。</span><span class="sxs-lookup"><span data-stu-id="f09ff-142">All services packs are supported, unless the service pack is specifically listed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f09ff-143">本节内容</span><span class="sxs-lookup"><span data-stu-id="f09ff-143">In This Section</span></span>  
  
[<span data-ttu-id="f09ff-144">最佳做法和建议为 FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="f09ff-144">Best practices and recommendations for the FTP Adapter</span></span>](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)  

[<span data-ttu-id="f09ff-145">配置 FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="f09ff-145">Configuring the FTP adapter</span></span>](../core/configuring-the-ftp-adapter.md)  

[<span data-ttu-id="f09ff-146">FTP 适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="f09ff-146">FTP Adapter Property Schema and Properties</span></span>](../core/ftp-adapter-property-schema-and-properties.md)