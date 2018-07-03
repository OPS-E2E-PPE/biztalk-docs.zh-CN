---
title: 开始使用用于 Siebel eBusiness 应用程序的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, about
ms.assetid: 0867f95f-977f-48bf-8c46-70fd6e4df56b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f4d03e8b85811db6ea7fe7bcde5bf37f93b255d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968942"
---
# <a name="get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="ecce6-102">开始使用用于 Siebel eBusiness 应用程序的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="ecce6-102">Get started with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="ecce6-103">本部分中的用户不熟悉 Microsoft 提供的适配器、 先决条件和主题概述[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ecce6-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="ecce6-104">它讨论的功能[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]和可以使用该适配器在 Siebel 系统执行不同操作。</span><span class="sxs-lookup"><span data-stu-id="ecce6-104">It discusses the features of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] and the different operations that can be performed on the Siebel system using the adapter.</span></span>  
  
 <span data-ttu-id="ecce6-105">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="ecce6-105">What is an adapter?</span></span> <span data-ttu-id="ecce6-106">适配器是一个软件组件，可用于发送和接收消息与业务 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="ecce6-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="ecce6-107">适配器的主要设计目标是方便贸易合作伙伴之间业务文档交换。</span><span class="sxs-lookup"><span data-stu-id="ecce6-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="ecce6-108">由于每个业务系统可能需要遵照特定的文档格式和协议，适配器必须使用符合可识别的常用标准和协议的传送机制。</span><span class="sxs-lookup"><span data-stu-id="ecce6-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="ecce6-109">适配器可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="ecce6-109">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="ecce6-110">**LOB 适配器**。</span><span class="sxs-lookup"><span data-stu-id="ecce6-110">**LOB adapters**.</span></span> <span data-ttu-id="ecce6-111">此类适配器提供访问 LOB 系统的面向服务的编程模型 — 例如，对于 SAP 或 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="ecce6-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="ecce6-112">**数据适配器**。</span><span class="sxs-lookup"><span data-stu-id="ecce6-112">**Data adapters**.</span></span> <span data-ttu-id="ecce6-113">此类适配器提供了面向服务的编程模型访问数据库 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="ecce6-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="ecce6-114">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ecce6-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="ecce6-115"> ( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="ecce6-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="ecce6-116"> ( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="ecce6-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="ecce6-117"> ( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="ecce6-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="ecce6-118"> ( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="ecce6-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="ecce6-119"> ( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="ecce6-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="ecce6-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不适用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="ecce6-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="ecce6-121">如果您不已知道你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在贵公司，建议首先浏览功能和中所述的适配器的功能[概述的 BizTalk 适配器用于 Siebel eBusiness 应用程序](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ecce6-121">If you do not already know how you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Overview of BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecce6-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="ecce6-122">In This Section</span></span>  
  
-   [<span data-ttu-id="ecce6-123">了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="ecce6-123">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) 
  
-   [<span data-ttu-id="ecce6-124">Siebel 适配器教程</span><span class="sxs-lookup"><span data-stu-id="ecce6-124">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)  
  
-   [<span data-ttu-id="ecce6-125">社区资源</span><span class="sxs-lookup"><span data-stu-id="ecce6-125">Community Resources</span></span>](http://msdn.microsoft.com/library/ff5ec978-8cdd-418a-a25e-fd3746b64d8b)  
  
-   [<span data-ttu-id="ecce6-126">方面的常见问题</span><span class="sxs-lookup"><span data-stu-id="ecce6-126">Frequently Asked Questions</span></span>](http://msdn.microsoft.com/library/66953c15-08c5-48ac-a4ff-a72a82174f15)