---
title: 使用 BizTalk Server 轮询 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8180b3b671c87b5dcd0d41477e20b6d175f1cce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974214"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a><span data-ttu-id="ab5f4-102">使用 BizTalk Server 轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="ab5f4-102">Poll Oracle E-Business Suite using BizTalk Server</span></span>
<span data-ttu-id="ab5f4-103">你可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle 数据库接收基于轮询的消息。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="ab5f4-104">适配器提供轮询 Oracle 数据库的两种的方法：</span><span class="sxs-lookup"><span data-stu-id="ab5f4-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
- <span data-ttu-id="ab5f4-105">**使用 SELECT 语句**。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-105">**Using SELECT statements**.</span></span> <span data-ttu-id="ab5f4-106">可以指定一个简单的 SELECT 语句来轮询 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-106">You can specify a simple SELECT statement to poll the Oracle database.</span></span> <span data-ttu-id="ab5f4-107">适配器执行 SELECT 语句指定的时间间隔，并将结果返回到适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
- <span data-ttu-id="ab5f4-108">**使用存储的过程**。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-108">**Using stored procedures**.</span></span> <span data-ttu-id="ab5f4-109">您可以指定用于轮询 Oracle 数据库的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-109">You can specify a stored procedure to poll the Oracle database.</span></span> <span data-ttu-id="ab5f4-110">适配器在指定的时间间隔执行存储的过程，并将结果返回到适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-110">The adapter executes the stored procedure at specified intervals and returns the result to the adapter clients.</span></span>  
  
  <span data-ttu-id="ab5f4-111">中的两种方法的主要区别是方式适配器客户端指定用于轮询 Oracle 数据库适配器的轮询语句。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="ab5f4-112">简单的 SELECT 语句的轮询语句的第一种方法时，存储的过程方法的轮询语句是执行存储的过程的请求消息。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the stored procedure approach is a request message that executes the stored procedure.</span></span> <span data-ttu-id="ab5f4-113">适配器客户端为指定的轮询语句，这两种方法， **PollingInput**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-113">Adapter clients specify the polling statement, for either approach, for the **PollingInput** binding property.</span></span> <span data-ttu-id="ab5f4-114">有关绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-114">For more information about the binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
  <span data-ttu-id="ab5f4-115">在本部分中的主题提供有关如何使用 SELECT 语句和存储的过程轮询的说明。</span><span class="sxs-lookup"><span data-stu-id="ab5f4-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab5f4-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="ab5f4-116">In This Section</span></span>  
  
-   [<span data-ttu-id="ab5f4-117">使用 SELECT 语句轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="ab5f4-117">Poll Oracle E-Business Suite Using SELECT Statement</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [<span data-ttu-id="ab5f4-118">使用存储的过程轮询 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="ab5f4-118">Poll Oracle E-Business Suite Using Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab5f4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab5f4-119">See Also</span></span>  
[<span data-ttu-id="ab5f4-120">开发 BizTalk 应用程序使用 Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="ab5f4-120">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)