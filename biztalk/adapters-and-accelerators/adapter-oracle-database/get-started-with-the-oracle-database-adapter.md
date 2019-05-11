---
title: 开始使用 Oracle 数据库适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, about
- data adapter
- LOB adapter
ms.assetid: ed5b3510-11c4-4b10-bf85-c4066f3f80df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54d80b4e0f345a81d2b34215dec27085bad665dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376535"
---
# <a name="get-started-with-the-oracle-database-adapter"></a><span data-ttu-id="4c827-102">开始使用 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="4c827-102">Get started with the Oracle Database adapter</span></span>
<span data-ttu-id="4c827-103">本部分中的用户不熟悉 Microsoft 提供的适配器、 先决条件和主题概述[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c827-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="4c827-104">它讨论的功能[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]和可以使用该适配器在 Oracle 数据库执行不同操作。</span><span class="sxs-lookup"><span data-stu-id="4c827-104">It discusses the features of [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the different operations that can be performed on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="4c827-105">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="4c827-105">What is an adapter?</span></span> <span data-ttu-id="4c827-106">适配器是一个软件组件，可用于发送和接收消息与业务 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="4c827-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="4c827-107">适配器的主要设计目标是方便贸易合作伙伴之间业务文档交换。</span><span class="sxs-lookup"><span data-stu-id="4c827-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="4c827-108">因为每个业务系统可以遵守特定的文档格式和协议，该适配器将使用符合可识别的常用标准和协议的传送机制。</span><span class="sxs-lookup"><span data-stu-id="4c827-108">Because each business system can adhere to specific document formats and protocols, the adapter uses a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="4c827-109">适配器可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="4c827-109">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="4c827-110">**LOB 适配器**。</span><span class="sxs-lookup"><span data-stu-id="4c827-110">**LOB adapters**.</span></span> <span data-ttu-id="4c827-111">此类适配器提供访问 LOB 系统的面向服务的编程模型 — 例如，对于 SAP 或 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="4c827-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="4c827-112">**数据适配器**。</span><span class="sxs-lookup"><span data-stu-id="4c827-112">**Data adapters**.</span></span> <span data-ttu-id="4c827-113">此类适配器提供了面向服务的编程模型访问数据库 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="4c827-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="4c827-114">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4c827-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] <span data-ttu-id="4c827-115">( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="4c827-115">(the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="4c827-116">( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="4c827-116">(the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] <span data-ttu-id="4c827-117">( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="4c827-117">(the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] <span data-ttu-id="4c827-118">( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="4c827-118">(the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] <span data-ttu-id="4c827-119">( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="4c827-119">(the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="4c827-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不适用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="4c827-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="4c827-121">如果您不已知道你想要使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在贵公司，建议首先浏览功能和中所述的适配器的功能[BizTalk 适配器了解用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="4c827-121">If you do not already know how you want to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understanding the BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span></span>  
  
