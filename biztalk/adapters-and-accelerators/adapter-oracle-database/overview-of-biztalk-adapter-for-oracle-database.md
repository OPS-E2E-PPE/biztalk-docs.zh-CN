---
title: 用于 Oracle 数据库的 BizTalk Adapter 概述 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, overview
- ODP.NET
- Oracle Data Provider for .NET 2.0
ms.assetid: 852b8f82-ab34-45b8-ad7f-263d719a87f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b874b5523256342a4e8ae14b2c475ede11fe279
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214205"
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="bb6ee-102">用于 Oracle 数据库的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="bb6ee-102">Overview of BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="bb6ee-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开作为 WCF 服务的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes the Oracle database as a WCF service.</span></span> <span data-ttu-id="bb6ee-104">适配器客户端可以通过交换 SOAP 消息与适配器执行对 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-104">Adapter clients can perform operations on the Oracle database by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="bb6ee-105">适配器使用 WCF 消息，并且相应 ODP.NET 调用来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-105">The adapter consumes the WCF message and makes appropriate ODP.NET calls to perform the operation.</span></span> <span data-ttu-id="bb6ee-106">适配器回客户端的 SOAP 消息的形式，从 Oracle 数据库中返回响应。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-106">The adapter returns the response from the Oracle database back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="bb6ee-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]曲面描述元数据的 Oracle 数据库项目 （表、 函数、 过程等） 的结构的 SOAP 消息的 WSDL 形式。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces metadata of Oracle database artifacts (tables, functions, procedures, etc.) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="bb6ee-108">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，和[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]才能使适配器客户端检索操作的元数据并在编程解决方案中生成可用的编程项目。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-108">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], and [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="bb6ee-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 Oracle 数据提供程序的.NET (ODP.NET) 与 Oracle 数据库通信。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the Oracle Data Provider for .NET (ODP.NET) to communicate with the Oracle database.</span></span> <span data-ttu-id="bb6ee-110">你可以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与 Oracle 数据库通信通过以下方式：</span><span class="sxs-lookup"><span data-stu-id="bb6ee-110">You can use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to communicate with the Oracle database in the following ways:</span></span>  
  
-   <span data-ttu-id="bb6ee-111">通过开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-111">By developing BizTalk applications.</span></span> <span data-ttu-id="bb6ee-112">请参阅[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-112">See [Develop your BizTalk applications](../../core/develop-your-biztalk-applications.md) for more information.</span></span>  
  
-   <span data-ttu-id="bb6ee-113">通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-113">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="bb6ee-114">请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-114">See [Develop Oracle Database applications using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) for more information.</span></span>  
  
-   <span data-ttu-id="bb6ee-115">通过使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-115">By using the WCF channel model.</span></span> <span data-ttu-id="bb6ee-116">请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb6ee-116">See [Develop Oracle Database applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) for more information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb6ee-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="bb6ee-117">In This Section</span></span>  
  
-   <span data-ttu-id="bb6ee-118">[适配器如何连接到 Oracle 数据库？](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="bb6ee-118">[How Does the Adapter Connect to an Oracle Database?](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="bb6ee-119">[原理适配器图面 Oracle 元数据是什么？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="bb6ee-119">[How Does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="bb6ee-120">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="bb6ee-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>  
  
-   [<span data-ttu-id="bb6ee-121">如何执行适配器处理事务？</span><span class="sxs-lookup"><span data-stu-id="bb6ee-121">How does the Adapter Handle Transactions?</span></span>](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [<span data-ttu-id="bb6ee-122">Oracle 数据库中的 LOB 数据类型的流式处理支持</span><span class="sxs-lookup"><span data-stu-id="bb6ee-122">Streaming Support for LOB Data Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="bb6ee-123">Oracle 数据库适配器支持何种操作</span><span class="sxs-lookup"><span data-stu-id="bb6ee-123">What operations are supported by the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb6ee-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb6ee-124">See Also</span></span>  
 [<span data-ttu-id="bb6ee-125">了解 Biztalk 适配器用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="bb6ee-125">Understanding the Biztalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)