---
title: 开始使用用于 mySAP Business Suite 的 BizTalk 适配器 |Microsoft Docs
description: 安装自定义 Rfc，了解有关适配器的信息，完成 SAP，单步执行教程，可以使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器上的 RFC 和 IDOC 任务
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02112b6974a537c9f66cc301014ae16bb4bf326f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967463"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="38104-103">开始使用用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="38104-103">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="38104-104">本部分中的用户不熟悉 Microsoft 提供的适配器、 先决条件和主题概述[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="38104-104">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="38104-105">它讨论的功能[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]和可以使用该适配器在 SAP 系统执行不同操作。</span><span class="sxs-lookup"><span data-stu-id="38104-105">It discusses the features of [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the different operations that can be performed on the SAP system using the adapter.</span></span>  

## <a name="what-is-an-adapter"></a><span data-ttu-id="38104-106">什么是适配器？</span><span class="sxs-lookup"><span data-stu-id="38104-106">What is an adapter?</span></span> 
<span data-ttu-id="38104-107">适配器是一个软件组件，可用于发送和接收消息与业务 (LOB) 系统。</span><span class="sxs-lookup"><span data-stu-id="38104-107">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="38104-108">适配器的主要设计目标是方便贸易合作伙伴之间业务文档交换。</span><span class="sxs-lookup"><span data-stu-id="38104-108">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="38104-109">由于每个业务系统可能需要遵照特定的文档格式和协议，适配器必须使用符合可识别的常用标准和协议来向用户提供统一接口的传送机制。</span><span class="sxs-lookup"><span data-stu-id="38104-109">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="38104-110">适配器可以分为两大类：</span><span class="sxs-lookup"><span data-stu-id="38104-110">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="38104-111">**LOB 适配器**。</span><span class="sxs-lookup"><span data-stu-id="38104-111">**LOB adapters**.</span></span> <span data-ttu-id="38104-112">此类适配器提供与访问 LOB 系统的面向服务的编程模型 — 例如，对于 SAP 或 Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="38104-112">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="38104-113">**数据适配器**。</span><span class="sxs-lookup"><span data-stu-id="38104-113">**Data adapters**.</span></span> <span data-ttu-id="38104-114">此类适配器提供面向服务的访问的数据库的编程模型 — 例如，Oracle 数据库或 SQL Server 的适配器。</span><span class="sxs-lookup"><span data-stu-id="38104-114">Such adapters provide service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="38104-115">有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="38104-115">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="38104-116"> ( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="38104-116"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="38104-117"> ( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="38104-117"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="38104-118"> ( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="38104-118"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="38104-119"> ( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="38104-119"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="38104-120"> ( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="38104-120"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="38104-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不适用于 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="38104-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="38104-122">如果您不已知道你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在贵公司，建议首先浏览功能和中所述的适配器的功能[理解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="38104-122">If you do not already know how you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] at your company, it is recommended that you start by exploring features and functionality of the adapter described in [Understand BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="38104-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="38104-123">Next steps</span></span>  
- [<span data-ttu-id="38104-124">为 SAP 数据提供程序安装自定义 RFC</span><span class="sxs-lookup"><span data-stu-id="38104-124">Install Custom RFCs for the Data Provider for SAP</span></span>](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [<span data-ttu-id="38104-125">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="38104-125">Understand BizTalk Adapter for mySAP Business Suite</span></span>](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [<span data-ttu-id="38104-126">在 SAP 上完成 RFC 和 IDOC 任务</span><span class="sxs-lookup"><span data-stu-id="38104-126">Complete RFC and IDOC tasks on SAP</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [<span data-ttu-id="38104-127">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="38104-127">SAP Adapter Tutorials</span></span>](sap-adapter-tutorials.md)  