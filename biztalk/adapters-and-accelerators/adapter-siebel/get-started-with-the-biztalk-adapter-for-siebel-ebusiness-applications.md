---
title: "要开始使用用于 Siebel eBusiness Applications 的 BizTalk Adapter |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapters, about
ms.assetid: 0867f95f-977f-48bf-8c46-70fd6e4df56b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba067d0479bbcdae6d04c3affdcb9ee60e564cc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="9cd80-102">要开始使用用于 Siebel eBusiness Applications 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="9cd80-102">Get started with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="9cd80-103">本部分提供的适配器、 先决条件和主题概述的用户的不熟悉 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9cd80-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="9cd80-104">它讨论的功能[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]和可以在使用该适配器的 Siebel 系统执行不同操作。</span><span class="sxs-lookup"><span data-stu-id="9cd80-104">It discusses the features of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] and the different operations that can be performed on the Siebel system using the adapter.</span></span>  
  
 <span data-ttu-id="9cd80-105">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="9cd80-105">What is an adapter?</span></span> <span data-ttu-id="9cd80-106">适配器是一个软件组件，使您能够发送和接收消息传入和传出的业务线 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="9cd80-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="9cd80-107">适配器的主要设计目标是便于贸易合作伙伴之间的业务文档的交换。</span><span class="sxs-lookup"><span data-stu-id="9cd80-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="9cd80-108">由于每个业务系统可能符合特定的文档格式和协议，适配器必须使用符合公认的标准和协议的传递机制。</span><span class="sxs-lookup"><span data-stu-id="9cd80-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="9cd80-109">适配器可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="9cd80-109">The adapters can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="9cd80-110">**LOB 适配器**。</span><span class="sxs-lookup"><span data-stu-id="9cd80-110">**LOB adapters**.</span></span> <span data-ttu-id="9cd80-111">该类型的适配器提供面向服务的编程模型来访问 LOB 系统 — 例如，为 SAP 或 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="9cd80-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="9cd80-112">**数据适配器**。</span><span class="sxs-lookup"><span data-stu-id="9cd80-112">**Data adapters**.</span></span> <span data-ttu-id="9cd80-113">该类型的适配器提供面向服务的编程模型来访问数据库 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="9cd80-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="9cd80-114">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9cd80-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="9cd80-115">( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9cd80-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="9cd80-116">( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9cd80-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="9cd80-117">( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9cd80-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="9cd80-118">( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9cd80-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="9cd80-119">( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9cd80-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9cd80-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不可用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="9cd80-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="9cd80-121">如果你不已知道你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在贵公司，建议你首先探索功能和中所述的适配器的功能[概述的 BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span><span class="sxs-lookup"><span data-stu-id="9cd80-121">If you do not already know how you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Overview of BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9cd80-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="9cd80-122">In This Section</span></span>  
  
-   [<span data-ttu-id="9cd80-123">为 Siebel eBusiness 应用程序了解的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="9cd80-123">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) 
  
-   [<span data-ttu-id="9cd80-124">Siebel 适配器教程</span><span class="sxs-lookup"><span data-stu-id="9cd80-124">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)  
  
-   [<span data-ttu-id="9cd80-125">社区资源</span><span class="sxs-lookup"><span data-stu-id="9cd80-125">Community Resources</span></span>](http://msdn.microsoft.com/library/ff5ec978-8cdd-418a-a25e-fd3746b64d8b)  
  
-   [<span data-ttu-id="9cd80-126">常见问题</span><span class="sxs-lookup"><span data-stu-id="9cd80-126">Frequently Asked Questions</span></span>](http://msdn.microsoft.com/library/66953c15-08c5-48ac-a4ff-a72a82174f15)