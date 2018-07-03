---
title: 创建连接到 SQL Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7c5f186a28f068f3ffc217ce5f252a1512f03a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978006"
---
# <a name="create-a-connection-to-sql-server"></a><span data-ttu-id="5c9ad-102">创建与 SQL Server 的连接</span><span class="sxs-lookup"><span data-stu-id="5c9ad-102">Create a connection to SQL Server</span></span>
<span data-ttu-id="5c9ad-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="5c9ad-104">在这种情况下，它使到 SQL Server 数据库通过 WCF 终结点地址的通信。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-104">As such, it enables communication to a SQL Server database through a WCF endpoint address.</span></span> <span data-ttu-id="5c9ad-105">在 WCF 中，终结点地址标识服务的网络位置，并通常都表示为统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-105">In WCF, the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="5c9ad-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于建立与 SQL Server 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="5c9ad-107">必须指定连接 URI 时您：</span><span class="sxs-lookup"><span data-stu-id="5c9ad-107">You must specify a connection URI when you:</span></span>  
  
- <span data-ttu-id="5c9ad-108">创建通道工厂或通道侦听器使用的 WCF 通道模型或创建 WCF 客户端或服务主机使用 WCF 服务模型时。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-108">Create a channel factory or a channel listener using the WCF channel model or when you create a WCF client or service host using the WCF service model.</span></span>  
  
- <span data-ttu-id="5c9ad-109">创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="5c9ad-110">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
- <span data-ttu-id="5c9ad-111">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]BizTalk Server 解决方案。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] for a BizTalk Server solution.</span></span>  
  
- <span data-ttu-id="5c9ad-112">使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
  <span data-ttu-id="5c9ad-113">在本部分中的主题介绍如何建立之间的连接[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和，它可以提供与 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="5c9ad-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the SQL Server database by providing you with:</span></span>  
  
- <span data-ttu-id="5c9ad-114">有关连接属性和 SQL Server 连接 URI 的结构信息。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-114">Information about the connection properties and the structure of the SQL Server connection URI.</span></span>  
  
- <span data-ttu-id="5c9ad-115">演示如何通过使用指定连接 URI 的主题的链接[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-115">Links to topics that show how to specify a connection URI by using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="5c9ad-116">有关连接到 SQL Server 使用 Windows 身份验证的信息。</span><span class="sxs-lookup"><span data-stu-id="5c9ad-116">Information about connecting to SQL Server using Windows Authentication.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="5c9ad-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c9ad-117">See Also</span></span>  
[<span data-ttu-id="5c9ad-118">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="5c9ad-118">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)