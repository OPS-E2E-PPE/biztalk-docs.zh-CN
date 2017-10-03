---
title: "创建与 SQL Server 的连接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b87b4141c9e14c680d8100a7c505dda0a0093c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-sql-server"></a><span data-ttu-id="65777-102">创建与 SQL Server 的连接</span><span class="sxs-lookup"><span data-stu-id="65777-102">Create a connection to SQL Server</span></span>
<span data-ttu-id="65777-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="65777-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="65777-104">在这种情况下，它使到 SQL Server 数据库通过 WCF 终结点地址的通信。</span><span class="sxs-lookup"><span data-stu-id="65777-104">As such, it enables communication to a SQL Server database through a WCF endpoint address.</span></span> <span data-ttu-id="65777-105">在 WCF 中，终结点地址将标识服务的网络位置，并通常表示为统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="65777-105">In WCF, the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="65777-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]表示此位置作为连接 URI，其中包含属性的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于建立与 SQL Server 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="65777-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="65777-107">必须指定连接 URI 时你：</span><span class="sxs-lookup"><span data-stu-id="65777-107">You must specify a connection URI when you:</span></span>  
  
-   <span data-ttu-id="65777-108">创建通道工厂或通道侦听器使用 WCF 通道模型或当你创建使用 WCF 服务模型的 WCF 客户端或服务主机。</span><span class="sxs-lookup"><span data-stu-id="65777-108">Create a channel factory or a channel listener using the WCF channel model or when you create a WCF client or service host using the WCF service model.</span></span>  
  
-   <span data-ttu-id="65777-109">创建中的物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="65777-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="65777-110">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="65777-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
-   <span data-ttu-id="65777-111">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]检索消息架构从[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]BizTalk Server 解决方案。</span><span class="sxs-lookup"><span data-stu-id="65777-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] for a BizTalk Server solution.</span></span>  
  
-   <span data-ttu-id="65777-112">使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="65777-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
 <span data-ttu-id="65777-113">本部分中的主题介绍如何之间建立连接[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和通过为您提供了 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="65777-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the SQL Server database by providing you with:</span></span>  
  
-   <span data-ttu-id="65777-114">有关连接属性和 SQL Server 连接 URI 的结构信息。</span><span class="sxs-lookup"><span data-stu-id="65777-114">Information about the connection properties and the structure of the SQL Server connection URI.</span></span>  
  
-   <span data-ttu-id="65777-115">演示如何通过使用指定连接 URI 的主题的链接[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="65777-115">Links to topics that show how to specify a connection URI by using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="65777-116">有关连接到 SQL Server 使用 Windows 身份验证的信息。</span><span class="sxs-lookup"><span data-stu-id="65777-116">Information about connecting to SQL Server using Windows Authentication.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="65777-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65777-117">See Also</span></span>  
[<span data-ttu-id="65777-118">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="65777-118">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)