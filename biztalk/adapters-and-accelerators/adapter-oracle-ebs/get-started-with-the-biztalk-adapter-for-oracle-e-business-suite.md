---
title: "开始使用 BizTalk 适配器用于 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 852d5855-c58a-4fa3-8efd-6afea9e527df
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84c149c18da6d08283d0969b89a4634581b0001a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="9e4a4-102">开始使用 BizTalk 适配器用于 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="9e4a4-102">Get started with the BizTalk Adapter for Oracle E-Business Suite</span></span>
<span data-ttu-id="9e4a4-103">适配器、 先决条件和用户的 Microsoft BizTalk 适配器包的新主题的概述。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-103">Overview of the adapter, prerequisites, and topics for users who are new to Microsoft BizTalk Adapter Pack.</span></span> <span data-ttu-id="9e4a4-104">提供的功能有关的信息[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]和可以使用该适配器执行对 Oracle 数据库的不同运算。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-104">Information is provided about the features of [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] and the different operations that can be performed on the Oracle database by using the adapter.</span></span>  
  
## <a name="what-is-an-adapter"></a><span data-ttu-id="9e4a4-105">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="9e4a4-105">What is an adapter?</span></span>  
  
 <span data-ttu-id="9e4a4-106">适配器是一个软件组件，使您能够发送和接收消息传入和传出的业务线 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="9e4a4-107">适配器的主要目的是便于贸易合作伙伴之间的业务文档的交换。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-107">The primary goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="9e4a4-108">由于每个业务系统可能符合特定的文档格式和协议，适配器必须使用符合公认的标准和协议，以向用户提供统一的接口的传递机制。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="9e4a4-109">中的适配器[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="9e4a4-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="9e4a4-110">**LOB 适配器**: LOB 适配器提供面向服务的编程模型来访问 LOB 系统 — 例如，为 SAP 或 Siebel 应用程序的适配器。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-110">**LOB adapters**: LOB adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel applications.</span></span>  
  
-   <span data-ttu-id="9e4a4-111">**数据适配器**： 数据适配器提供面向服务的编程模型来访问数据库 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-111">**Data adapters**: Data adapters provide a service-oriented programming model to access databases — for example, adapters for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="9e4a4-112">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9e4a4-112">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="9e4a4-113"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9e4a4-113"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="9e4a4-114"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9e4a4-114"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="9e4a4-115"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9e4a4-115"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="9e4a4-116"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9e4a4-116"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="9e4a4-117"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9e4a4-117"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4a4-118">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不可用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-118">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="9e4a4-119">如果你不熟悉如何[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，我们建议你首先探索功能和功能的适配器中所述[了解用于 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="9e4a4-119">If you are new to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], then we recommend you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e4a4-120">在本节中</span><span class="sxs-lookup"><span data-stu-id="9e4a4-120">In this section</span></span>  
  
-   [<span data-ttu-id="9e4a4-121">了解有关 Oracle E-business Suite 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="9e4a4-121">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [<span data-ttu-id="9e4a4-122">教程： 从 SharePoint 站点上的 Oracle E-business Suite 提供数据</span><span class="sxs-lookup"><span data-stu-id="9e4a4-122">Tutorial: Presenting data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Presenting%20Data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)
  
- [<span data-ttu-id="9e4a4-123">故障排除 Oracle EBS 适配器</span><span class="sxs-lookup"><span data-stu-id="9e4a4-123">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)