---
title: 轮询 Oracle E-business Suite 使用的是 WCF 服务模型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96670a39-4fec-49bf-85d1-947b1a1bc750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0122bceddbfd902f31549efe9bc8819f108b6f57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215109"
---
# <a name="poll-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="964f6-102">使用 WCF 服务模型的轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="964f6-102">Poll Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="964f6-103">你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle 数据库接收基于轮询的消息。</span><span class="sxs-lookup"><span data-stu-id="964f6-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive polling-based messages from the Oracle database.</span></span> <span data-ttu-id="964f6-104">适配器提供轮询 Oracle 数据库的两种的方法：</span><span class="sxs-lookup"><span data-stu-id="964f6-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
-   <span data-ttu-id="964f6-105">**使用 SELECT 语句**。</span><span class="sxs-lookup"><span data-stu-id="964f6-105">**Using SELECT statements**.</span></span> <span data-ttu-id="964f6-106">你可以指定一个简单的 SELECT 语句来轮询 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="964f6-106">You can specify a simple SELECT statement to poll the Oracle database.</span></span> <span data-ttu-id="964f6-107">适配器执行 SELECT 语句指定时间间隔，并将结果返回给适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="964f6-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
-   <span data-ttu-id="964f6-108">**使用存储的过程**。</span><span class="sxs-lookup"><span data-stu-id="964f6-108">**Using stored procedures**.</span></span> <span data-ttu-id="964f6-109">你可以指定要轮询的 Oracle 数据库的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="964f6-109">You can specify a stored procedure to poll the Oracle database.</span></span> <span data-ttu-id="964f6-110">适配器在指定的时间间隔执行存储的过程，并将结果返回给适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="964f6-110">The adapter executes the stored procedure at specified intervals and returns the result to the adapter clients.</span></span>  
  
 <span data-ttu-id="964f6-111">在两个方法中的关键区别是方式适配器客户端指定适配器使用来轮询 Oracle 数据库的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="964f6-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="964f6-112">第一种方法的轮询语句时简单的 SELECT 语句，用于存储的过程方法的轮询语句是在执行存储的过程的请求消息。</span><span class="sxs-lookup"><span data-stu-id="964f6-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the stored procedure approach is a request message that executes the stored procedure.</span></span> <span data-ttu-id="964f6-113">适配器客户端为指定的轮询语句，这两种方法， **PollingInput**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="964f6-113">Adapter clients specify the polling statement, for either approach, for the **PollingInput** binding property.</span></span> <span data-ttu-id="964f6-114">有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="964f6-114">For more information about the binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
 <span data-ttu-id="964f6-115">本部分中的主题提供有关如何轮询使用 SELECT 语句和存储的过程的说明。</span><span class="sxs-lookup"><span data-stu-id="964f6-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="964f6-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="964f6-116">In This Section</span></span>  
  
-   [<span data-ttu-id="964f6-117">使用 WCF 服务模型使用 SELECT 语句的轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="964f6-117">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="964f6-118">轮询 Oracle E-business Suite 与 WCF 服务模型使用存储的过程</span><span class="sxs-lookup"><span data-stu-id="964f6-118">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="964f6-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="964f6-119">See Also</span></span>  
 [<span data-ttu-id="964f6-120">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="964f6-120">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)