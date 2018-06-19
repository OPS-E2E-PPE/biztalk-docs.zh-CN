---
title: 开发 SQL 应用程序使用 WCF 通道模型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11df5cc2-b532-45a8-9055-d05f4704a6e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b503b0766a4848e05c9361fb151196ee43afd81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222229"
---
# <a name="develop-sql-applications-using-the-wcf-channel-model"></a><span data-ttu-id="dfc45-102">开发 SQL 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="dfc45-102">Develop SQL applications using the WCF Channel Model</span></span>
<span data-ttu-id="dfc45-103">你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]通过直接通过使用 SQL Server 绑定创建的通道实例发送 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="dfc45-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] by sending XML messages directly over a channel instance created with the SQL Server Binding.</span></span>  
  
 <span data-ttu-id="dfc45-104">通过使用的强类型类和 WCF 服务模型公开的方法使用 WCF 通道模型的一个优点是通道模型提供的 SQL 数据库执行的操作的更好地细化控制。</span><span class="sxs-lookup"><span data-stu-id="dfc45-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the SQL database.</span></span> <span data-ttu-id="dfc45-105">此控件来自在 WCF 通道模型中，你直接控制通过通道发送的消息的内容的事实。</span><span class="sxs-lookup"><span data-stu-id="dfc45-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="dfc45-106">在某些情况下，此额外级别是控制的有益的。</span><span class="sxs-lookup"><span data-stu-id="dfc45-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="dfc45-107">例如，当使用 WCF 通道模型来执行更新操作在表上的，你有选择地可以直接更新目标行中的列，通过省略消息中传递的更新模板中的列。</span><span class="sxs-lookup"><span data-stu-id="dfc45-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="dfc45-108">仅有的列所需那些带有"nillable = false"WSDL 中。</span><span class="sxs-lookup"><span data-stu-id="dfc45-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="dfc45-109">由公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于表架构中包含的每个列的模板使用强类型的记录参数。</span><span class="sxs-lookup"><span data-stu-id="dfc45-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="dfc45-110">本主题中的各节说明如何执行操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="dfc45-110">The sections in this topic explain how to perform operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfc45-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="dfc45-111">In This Section</span></span>  
  
-   [<span data-ttu-id="dfc45-112">与 SQL 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="dfc45-112">Overview of the WCF channel model with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="dfc45-113">创建一个通道，使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="dfc45-113">Create a channel using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="dfc45-114">运行 SQL 使用 WCF 通道模型中的表上的插入操作</span><span class="sxs-lookup"><span data-stu-id="dfc45-114">Run an Insert Operation on a Table in SQL using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="dfc45-115">通过使用 WCF 通道模型从 SQL Server 接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="dfc45-115">Receive Polling-based Data-changed Messages from SQL Server by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)  
  
## <a name="see-also"></a><span data-ttu-id="dfc45-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfc45-116">See Also</span></span>  
[<span data-ttu-id="dfc45-117">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="dfc45-117">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)