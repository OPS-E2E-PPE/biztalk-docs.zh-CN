---
title: 开始使用的 BizTalk 适配器进行 SQL |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c3b6e36-ddfb-4ede-adf5-b9762231224b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a5021825d7e707b0f7f63935145986252ddc32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369413"
---
# <a name="get-started-with-the-biztalk-adapter-for-sql"></a><span data-ttu-id="5e4f2-102">开始使用的 BizTalk 适配器进行 SQL</span><span class="sxs-lookup"><span data-stu-id="5e4f2-102">Get started with the BizTalk adapter for SQL</span></span>

  
 <span data-ttu-id="5e4f2-103">本部分中的用户不熟悉 Microsoft 提供的适配器、 先决条件和主题概述[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="5e4f2-104">它讨论的功能[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]以及可以使用该适配器执行 SQL Server 数据库的不同操作。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-104">It discusses the features of [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the different operations that can be performed on the SQL Server database by using the adapter.</span></span>  
  
 <span data-ttu-id="5e4f2-105">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="5e4f2-105">What is an adapter?</span></span> <span data-ttu-id="5e4f2-106">适配器是一个软件组件，可用于发送和接收消息与业务 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="5e4f2-107">适配器的主要设计目标是方便贸易合作伙伴之间业务文档交换。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-107">The primary design goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="5e4f2-108">由于每个业务系统可能需要遵照特定的文档格式和协议，适配器必须使用符合可识别的常用标准和协议来向用户提供统一接口的传送机制。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="5e4f2-109">中的适配器[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="5e4f2-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="5e4f2-110">**LOB 适配器**。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-110">**LOB adapters**.</span></span> <span data-ttu-id="5e4f2-111">此类适配器提供与访问 LOB 系统的面向服务的编程模型 — 例如，对于 SAP 或 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-111">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="5e4f2-112">**数据适配器**。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-112">**Data adapters**.</span></span> <span data-ttu-id="5e4f2-113">此类适配器提供面向服务的访问的数据库的编程模型 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-113">Such adapters provide service-oriented programming model to access databases—for example, adapters for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="5e4f2-114">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5e4f2-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] <span data-ttu-id="5e4f2-115">([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e4f2-115">([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5e4f2-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]也是外部[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]作为一个单独的适配器。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is also available outside the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as a separate adapter.</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="5e4f2-117">([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e4f2-117">([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] <span data-ttu-id="5e4f2-118">([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e4f2-118">([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] <span data-ttu-id="5e4f2-119">([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e4f2-119">([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] <span data-ttu-id="5e4f2-120">([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5e4f2-120">([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5e4f2-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不适用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="5e4f2-122">如果您不已知道你想要在公司使用 SQL 适配器，则建议首先浏览功能和中所述的适配器的功能[了解 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4f2-122">If you do not already know how you want to use the SQL adapter at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e4f2-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="5e4f2-123">In This Section</span></span>  
  
-   [<span data-ttu-id="5e4f2-124">了解用于 SQL Server 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="5e4f2-124">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)  
  
-   [<span data-ttu-id="5e4f2-125">SQL 适配器教程</span><span class="sxs-lookup"><span data-stu-id="5e4f2-125">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)  
  
-   [<span data-ttu-id="5e4f2-126">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="5e4f2-126">Frequently Asked Questions</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-faqs.md)