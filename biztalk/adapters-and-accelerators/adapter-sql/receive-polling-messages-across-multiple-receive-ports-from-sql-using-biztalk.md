---
title: 从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 21cf4875-1c04-41cf-98f5-d1307987ca55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f7be558dfcd5939836143e361f4b3a76850701
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368713"
---
# <a name="receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk-server"></a><span data-ttu-id="0f1a3-102">从 SQL 使用 BizTalk Server 接收轮询消息跨多个接收端口</span><span class="sxs-lookup"><span data-stu-id="0f1a3-102">Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server</span></span>
<span data-ttu-id="0f1a3-103">假设你想要创建包含两个轮询操作的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-103">Consider a scenario where you want to create a BizTalk application that includes two polling operations.</span></span> <span data-ttu-id="0f1a3-104">每个轮询操作轮询单独的表，员工和客户，从同一个数据库。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-104">Each polling operation polls separate tables, Employee and Customer, from the same database.</span></span> <span data-ttu-id="0f1a3-105">在此类应用程序的部署时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你将需要创建两个接收端口。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-105">When you deploy such an application in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you will need to create two receive ports.</span></span> <span data-ttu-id="0f1a3-106">连接 URI 为每个接收端口将是：</span><span class="sxs-lookup"><span data-stu-id="0f1a3-106">The connection URI for each receive port will be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>  
```  
  
 <span data-ttu-id="0f1a3-107">因为这两个接收端口将从同一台服务器上的相同数据库接收轮询消息、 连接 URI 的同时将相同。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-107">Because both receive ports are receiving polling messages from the same database on the same server, the connection URI for both will be the same.</span></span> <span data-ttu-id="0f1a3-108">但是，BizTalk 应用程序不能有两个接收端口与同一个连接 URI。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-108">However, a BizTalk application cannot have two receive ports with the same connection URI.</span></span>  
  
 <span data-ttu-id="0f1a3-109">若要启用适配器客户端有两个 BizTalk 应用程序中的接收轮询同一数据库 （或甚至在数据库中的同一个表） 的端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供了连接属性**InboundID**。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-109">To enable adapter clients to have two receive ports that poll the same database (or even the same table in a database) in a BizTalk application, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides a connection property, **InboundID**.</span></span> <span data-ttu-id="0f1a3-110">可以指定此连接属性的任何值。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-110">You can specify any value for this connection property.</span></span> <span data-ttu-id="0f1a3-111">通过添加入站的 ID，一个连接 URI 变得唯一。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-111">By adding the inbound ID, a connection URI becomes unique.</span></span> <span data-ttu-id="0f1a3-112">例如：</span><span class="sxs-lookup"><span data-stu-id="0f1a3-112">For example:</span></span>  
  
 <span data-ttu-id="0f1a3-113">为端口接收轮询消息为 Employee 表的连接 URI 可以是：</span><span class="sxs-lookup"><span data-stu-id="0f1a3-113">The connection URI for the port receiving polling messages for the Employee table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Employee  
```  
  
 <span data-ttu-id="0f1a3-114">同样，为端口接收轮询消息的 Customer 表的连接 URI 可以是：</span><span class="sxs-lookup"><span data-stu-id="0f1a3-114">Similarly, the connection URI for the port receiving polling messages for the Customer table can be:</span></span>  
  
```  
mssql://<server_name>/<database_instance_name>/<datbase_name>?InboundID=Customer  
```  
  
 <span data-ttu-id="0f1a3-115">因为通过添加连接 Uri 变得唯一**InboundID**属性，可以现在有多个接收端口轮询同一数据库或单个 BizTalk 应用程序中的表。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-115">Because the connection URIs become unique by adding the **InboundID** property, you can now have multiple receive ports polling the same database or table in a single BizTalk application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0f1a3-116">您可以选择指定**InboundID**两个连接属性**轮询**并**TypedPolling**操作。</span><span class="sxs-lookup"><span data-stu-id="0f1a3-116">You can choose to specify the **InboundID** connection property for both the **Polling** and **TypedPolling** operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f1a3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f1a3-117">See Also</span></span>  
 [<span data-ttu-id="0f1a3-118">使用 SQL 适配器与 BizTalk Server 轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f1a3-118">Poll SQL Server using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)