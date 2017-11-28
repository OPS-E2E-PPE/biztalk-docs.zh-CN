---
title: "管理 MessageBox 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e854ad0f7014de8241f8a7b6af6addd49cb4da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-messagebox-databases"></a><span data-ttu-id="84fd4-102">管理 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="84fd4-102">Managing MessageBox Databases</span></span>
<span data-ttu-id="84fd4-103">MessageBox 数据库具有三种基本功能。</span><span class="sxs-lookup"><span data-stu-id="84fd4-103">The MessageBox database has three essential functions.</span></span> <span data-ttu-id="84fd4-104">它可存储订阅和跟踪信息，还可将消息送达与订阅相匹配的服务。</span><span class="sxs-lookup"><span data-stu-id="84fd4-104">It stores subscriptions and tracking information and it delivers the messages to the services that match the subscriptions.</span></span> <span data-ttu-id="84fd4-105">MessageBox 数据库是一种为每台 BizTalk 主机存储队列和状态表的主机平台。</span><span class="sxs-lookup"><span data-stu-id="84fd4-105">The MessageBox database is a host platform that stores the queues and state tables for each BizTalk Host.</span></span> <span data-ttu-id="84fd4-106">MessageBox 数据库还可存储消息和消息属性。</span><span class="sxs-lookup"><span data-stu-id="84fd4-106">The MessageBox database also stores messages and message properties.</span></span>  
  
 <span data-ttu-id="84fd4-107">如果 MessageBox 数据库在您的环境中属于具有高暴露风险的资产，建议使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 以限制与 MessageBox 的通信并确保通信安全。</span><span class="sxs-lookup"><span data-stu-id="84fd4-107">If the MessageBox databases are an asset with high-risk exposure in your environment, we recommend that you use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to restrict and secure communication to and from the MessageBox databases.</span></span>  
  
 <span data-ttu-id="84fd4-108">如果使用 Windows Server 2003，则必须对 MessageBox 数据库启用分布式事务处理协调器 (DTC)。</span><span class="sxs-lookup"><span data-stu-id="84fd4-108">If you use Windows Server 2003, you must enable the distributed transaction coordinator (DTC) on the MessageBox database.</span></span> <span data-ttu-id="84fd4-109">还必须为多计算机部署启用网络客户端。</span><span class="sxs-lookup"><span data-stu-id="84fd4-109">You must also enable network clients for multicomputer deployments.</span></span> <span data-ttu-id="84fd4-110">有关详细信息，请参阅[管理服务器的端口](../core/ports-for-the-administration-server.md)。</span><span class="sxs-lookup"><span data-stu-id="84fd4-110">For more information, see [Ports for the Administration Server](../core/ports-for-the-administration-server.md).</span></span>  
  
 <span data-ttu-id="84fd4-111">本部分包含有关管理您的环境中的 MessageBox 数据库的过程信息。</span><span class="sxs-lookup"><span data-stu-id="84fd4-111">This section contains procedural information about managing MessageBox databases in your environment.</span></span> <span data-ttu-id="84fd4-112">有关概念性信息 MessageBox 数据库和订阅模型 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用来处理消息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。</span><span class="sxs-lookup"><span data-stu-id="84fd4-112">For conceptual information about MessageBox databases and the subscription model Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to process messages, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84fd4-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="84fd4-113">In This Section</span></span>  
  
-   [<span data-ttu-id="84fd4-114">如何添加新的 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="84fd4-114">How to Add a New MessageBox Database</span></span>](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [<span data-ttu-id="84fd4-115">如何禁用发布新消息</span><span class="sxs-lookup"><span data-stu-id="84fd4-115">How to Disable New Message Publication</span></span>](../core/how-to-disable-new-message-publication.md)  
  
-   [<span data-ttu-id="84fd4-116">如何删除 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="84fd4-116">How to Delete a MessageBox Database</span></span>](../core/how-to-delete-a-messagebox-database.md)