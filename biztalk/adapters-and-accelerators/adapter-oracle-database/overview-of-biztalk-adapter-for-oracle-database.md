---
title: 用于 Oracle 数据库的 BizTalk 适配器概述 |Microsoft Docs
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
ms.openlocfilehash: 0d6629672ac1bbfdd5e0bc4e01cee37c5d71d137
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005174"
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="94d14-102">用于 Oracle 数据库的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="94d14-102">Overview of BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="94d14-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开为 WCF 服务的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="94d14-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes the Oracle database as a WCF service.</span></span> <span data-ttu-id="94d14-104">适配器客户端可以通过交换 SOAP 消息与适配器执行对 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="94d14-104">Adapter clients can perform operations on the Oracle database by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="94d14-105">适配器使用 WCF 消息并调用相应 ODP.NET 来执行该操作。</span><span class="sxs-lookup"><span data-stu-id="94d14-105">The adapter consumes the WCF message and makes appropriate ODP.NET calls to perform the operation.</span></span> <span data-ttu-id="94d14-106">适配器返回到 SOAP 消息的窗体中的客户端，并将响应返回从 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="94d14-106">The adapter returns the response from the Oracle database back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="94d14-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]的 Oracle 数据库项目 （表、 函数、 过程等） 的图面元数据描述结构的 SOAP 消息的 WSDL 格式。</span><span class="sxs-lookup"><span data-stu-id="94d14-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces metadata of Oracle database artifacts (tables, functions, procedures, etc.) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="94d14-108">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]， [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，和[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]启用适配器客户端来检索操作的元数据，并在生成的编程项目，可以使用编程解决方案中。</span><span class="sxs-lookup"><span data-stu-id="94d14-108">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], and [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="94d14-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 Oracle 数据提供程序的.NET (ODP.NET) 与 Oracle 数据库进行通信。</span><span class="sxs-lookup"><span data-stu-id="94d14-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the Oracle Data Provider for .NET (ODP.NET) to communicate with the Oracle database.</span></span> <span data-ttu-id="94d14-110">可以使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以以下方式与 Oracle 数据库进行通信：</span><span class="sxs-lookup"><span data-stu-id="94d14-110">You can use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to communicate with the Oracle database in the following ways:</span></span>  
  
- <span data-ttu-id="94d14-111">通过开发 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="94d14-111">By developing BizTalk applications.</span></span> <span data-ttu-id="94d14-112">请参阅[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="94d14-112">See [Develop your BizTalk applications](../../core/develop-your-biztalk-applications.md) for more information.</span></span>  
  
- <span data-ttu-id="94d14-113">通过使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="94d14-113">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="94d14-114">请参阅[开发 Oracle 数据库应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="94d14-114">See [Develop Oracle Database applications using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) for more information.</span></span>  
  
- <span data-ttu-id="94d14-115">通过使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="94d14-115">By using the WCF channel model.</span></span> <span data-ttu-id="94d14-116">请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="94d14-116">See [Develop Oracle Database applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) for more information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94d14-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="94d14-117">In This Section</span></span>  
  
-   <span data-ttu-id="94d14-118">[适配器如何连接到 Oracle 数据库？](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="94d14-118">[How Does the Adapter Connect to an Oracle Database?](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="94d14-119">[原理适配器图面上的 Oracle 元数据是什么？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="94d14-119">[How Does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="94d14-120">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="94d14-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>  
  
-   [<span data-ttu-id="94d14-121">原理适配器处理事务是什么？</span><span class="sxs-lookup"><span data-stu-id="94d14-121">How does the Adapter Handle Transactions?</span></span>](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [<span data-ttu-id="94d14-122">Oracle 数据库中的 LOB 数据类型的流支持</span><span class="sxs-lookup"><span data-stu-id="94d14-122">Streaming Support for LOB Data Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="94d14-123">哪些操作支持的 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="94d14-123">What operations are supported by the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="94d14-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="94d14-124">See Also</span></span>  
 [<span data-ttu-id="94d14-125">了解用于 Oracle 数据库的 Biztalk 适配器</span><span class="sxs-lookup"><span data-stu-id="94d14-125">Understanding the Biztalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)