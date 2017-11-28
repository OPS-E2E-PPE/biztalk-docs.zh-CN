---
title: "要开始使用 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, about
- data adapter
- LOB adapter
ms.assetid: ed5b3510-11c4-4b10-bf85-c4066f3f80df
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7aa93ae3f64f4f2f914a51508a3a8dee4e3be41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-oracle-database-adapter"></a><span data-ttu-id="70a19-102">要开始使用 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="70a19-102">Get started with the Oracle Database adapter</span></span>
<span data-ttu-id="70a19-103">本部分提供的适配器、 先决条件和主题概述的用户的不熟悉 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="70a19-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="70a19-104">它讨论的功能[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]和可以在使用该适配器的 Oracle 数据库执行不同操作。</span><span class="sxs-lookup"><span data-stu-id="70a19-104">It discusses the features of [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the different operations that can be performed on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="70a19-105">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="70a19-105">What is an adapter?</span></span> <span data-ttu-id="70a19-106">适配器是一个软件组件，使您能够发送和接收消息传入和传出的业务线 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="70a19-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="70a19-107">适配器的主要设计目标是便于贸易合作伙伴之间的业务文档的交换。</span><span class="sxs-lookup"><span data-stu-id="70a19-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="70a19-108">由于每个业务系统可以遵循特定的文档格式和协议，该适配器将使用符合公认的标准和协议的传递机制。</span><span class="sxs-lookup"><span data-stu-id="70a19-108">Because each business system can adhere to specific document formats and protocols, the adapter uses a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="70a19-109">适配器可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="70a19-109">The adapters can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="70a19-110">**LOB 适配器**。</span><span class="sxs-lookup"><span data-stu-id="70a19-110">**LOB adapters**.</span></span> <span data-ttu-id="70a19-111">该类型的适配器提供面向服务的编程模型来访问 LOB 系统 — 例如，为 SAP 或 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="70a19-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="70a19-112">**数据适配器**。</span><span class="sxs-lookup"><span data-stu-id="70a19-112">**Data adapters**.</span></span> <span data-ttu-id="70a19-113">该类型的适配器提供面向服务的编程模型来访问数据库 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="70a19-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="70a19-114">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="70a19-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="70a19-115"> ( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="70a19-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="70a19-116"> ( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="70a19-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="70a19-117"> ( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="70a19-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="70a19-118"> ( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="70a19-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="70a19-119"> ( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="70a19-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70a19-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不可用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="70a19-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="70a19-121">如果你不已知道你想要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在贵公司，建议你首先探索功能和中所述的适配器的功能[用于 Oracle 数据库了解BizTalk适配器](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="70a19-121">If you do not already know how you want to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understanding the BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span></span>  
  
