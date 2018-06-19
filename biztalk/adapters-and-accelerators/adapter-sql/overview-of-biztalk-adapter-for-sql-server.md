---
title: 用于 SQL Server 的 BizTalk Adapter 概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e46690e-d5c4-4d6b-b7a0-9a5adf4431cd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d0c1fd3ce3a9f07367b7cc75ffeeb98f84b119
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222741"
---
# <a name="overview-of-biztalk-adapter-for-sql-server"></a><span data-ttu-id="09ecc-102">用于 SQL Server 的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="09ecc-102">Overview of BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="09ecc-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开作为 WCF 服务的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="09ecc-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the SQL Server database as a WCF service.</span></span> <span data-ttu-id="09ecc-104">适配器客户端可以通过交换 SOAP 消息与适配器执行 SQL Server 数据库上的操作。</span><span class="sxs-lookup"><span data-stu-id="09ecc-104">Adapter clients can perform operations on the SQL Server database by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="09ecc-105">适配器使用 SOAP 消息，并且相应的 ADO.NET 调用来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="09ecc-105">The adapter consumes the SOAP message and makes appropriate ADO.NET calls to perform the operation.</span></span> <span data-ttu-id="09ecc-106">适配器回客户端的 SOAP 消息的形式从 SQL Server 数据库返回响应。</span><span class="sxs-lookup"><span data-stu-id="09ecc-106">The adapter returns the response from the SQL Server database back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="09ecc-107">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]曲面元数据 （如表、 视图和过程） 的 SQL Server 数据库中的项目。</span><span class="sxs-lookup"><span data-stu-id="09ecc-107">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] surfaces metadata of artifacts in the SQL Server database (such as tables, views, and procedures).</span></span>  <span data-ttu-id="09ecc-108">此元数据描述窗体的 Web 服务描述语言 (WSDL) 中的 SOAP 消息的结构。</span><span class="sxs-lookup"><span data-stu-id="09ecc-108">This metadata describes the structure of a SOAP message in the form of Web Services Description Language (WSDL).</span></span> <span data-ttu-id="09ecc-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]才能使适配器客户端检索操作的元数据。</span><span class="sxs-lookup"><span data-stu-id="09ecc-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations.</span></span> <span data-ttu-id="09ecc-110">适配器还编程解决方案中生成可用的编程项目。</span><span class="sxs-lookup"><span data-stu-id="09ecc-110">The adapter also generates programming artifacts that can be used in your programming solution.</span></span> <span data-ttu-id="09ecc-111">有关详细信息[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，请参阅[连接到使用 SQL 适配器的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="09ecc-111">For more information about [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], see [Connect to SQL Server in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
 <span data-ttu-id="09ecc-112">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 ADO.NET 与 SQL Server 数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="09ecc-112">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses ADO.NET to communicate with the SQL Server database.</span></span> <span data-ttu-id="09ecc-113">你可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可通过以下方式与 SQL Server 数据库进行通信：</span><span class="sxs-lookup"><span data-stu-id="09ecc-113">You can use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to communicate with the SQL Server database in the following ways:</span></span>  
  
-   <span data-ttu-id="09ecc-114">通过开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="09ecc-114">By developing BizTalk applications.</span></span> <span data-ttu-id="09ecc-115">有关详细信息，请参阅[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="09ecc-115">For more information, see [Develop BizTalk applications](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="09ecc-116">通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="09ecc-116">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="09ecc-117">有关详细信息，请参阅[开发应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="09ecc-117">For more information, see [Develop applications using the WCF Service model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="09ecc-118">通过使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="09ecc-118">By using the WCF channel model.</span></span> <span data-ttu-id="09ecc-119">有关详细信息，请参阅[开发应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="09ecc-119">For more information, see [Develop applications using the WCF Channel model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09ecc-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="09ecc-120">In This Section</span></span>  
  
-   [<span data-ttu-id="09ecc-121">适配器如何连接到 SQL Server？</span><span class="sxs-lookup"><span data-stu-id="09ecc-121">How Does the Adapter Connect to SQL Server?</span></span>](https://msdn.microsoft.com/library/dd788114.aspx) 
  
-   [<span data-ttu-id="09ecc-122">原理适配器图面 SQL 服务器元数据是什么？</span><span class="sxs-lookup"><span data-stu-id="09ecc-122">How Does the Adapter Surface SQL Server Metadata?</span></span>](https://msdn.microsoft.com/library/dd787941.aspx)  
  
-  <span data-ttu-id="09ecc-123">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="09ecc-123">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>  
  
-   [<span data-ttu-id="09ecc-124">哪些操作受 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="09ecc-124">What operations are supported by the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/what-operations-are-supported-by-the-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="09ecc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09ecc-125">See Also</span></span>  
 [<span data-ttu-id="09ecc-126">理解 SQL Server 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="09ecc-126">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)