---
title: BizTalk server 设计系统体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a18656a2d4d3827cd38a3f791af2ac856df8ce36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239269"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a><span data-ttu-id="1edc3-102">为 BizTalk Server 设计系统结构</span><span class="sxs-lookup"><span data-stu-id="1edc3-102">Designing the System Architectures for BizTalk Server</span></span>
<span data-ttu-id="1edc3-103">您的 Microsoft® BizTalk® Server 部署在安全性、性能、可用性和操作上的要求高度依赖于您的业务需求、要求、合作伙伴、公司规模等。</span><span class="sxs-lookup"><span data-stu-id="1edc3-103">The requirements of your Microsoft® BizTalk® Server deployment for security, performance, availability, and operation are highly dependent on your business needs, requirements, partners, company size, and so on.</span></span> <span data-ttu-id="1edc3-104">尽管将 BizTalk Server 组件的单个配置视为典型配置并为其提供说明性指导非常困难，但本部分还是就如何在分布式安全配置中为大型公司的生产环境配置不同的 BizTalk Server 功能提供了指导和建议。</span><span class="sxs-lookup"><span data-stu-id="1edc3-104">While it is difficult to consider any single configuration of BizTalk Server components as typical and provide prescriptive guidance for it, this section provides guidance and recommendations on how to configure the different BizTalk Server features in a distributed, secure configuration for the production environment of a large enterprise.</span></span>  
  
 <span data-ttu-id="1edc3-105">在本部分中介绍的结构旨在为您提供一些参考信息，帮助您了解如何在考虑采用深度防御的高度分布式环境中部署 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="1edc3-105">The architectures presented in this section aim to provide you with reference information about deploying BizTalk Server in a highly distributed environment where you take into consideration defense in depth.</span></span> <span data-ttu-id="1edc3-106">BizTalk Server 每个应用程序很可能具有其自己的基于问题域，使用的协议的安全要求的唯一集和解决方案的特定环境会在运行。</span><span class="sxs-lookup"><span data-stu-id="1edc3-106">Every application for BizTalk Server is likely to have its own unique set of security requirements based on the problem domain, the protocols used, and the particular environment the solution operates in.</span></span> <span data-ttu-id="1edc3-107">性能、 可用性和成本的考虑进一步影响这些要求。</span><span class="sxs-lookup"><span data-stu-id="1edc3-107">Performance, availability, and cost considerations further influence these requirements.</span></span> <span data-ttu-id="1edc3-108">您应以本文中的这些结构和建议为基础，针对您的公司的需求、威胁和资产创建自己的 BizTalk Server 部署。</span><span class="sxs-lookup"><span data-stu-id="1edc3-108">You should use these architectures and the recommendations within this document as the building blocks to create your own BizTalk Server deployment tailored to the needs, threats and assets of your company.</span></span>  
  
 <span data-ttu-id="1edc3-109">本部分中包含有关以下方面的信息：如何设计 BizTalk Server 的系统结构，以确保 BizTalk Server 中不同功能的安全，并从而确保服务器处理和存储的数据的安全；以及如何在分布式环境中放置服务器，以使在发生攻击或灾难事件时最大限度地减少可能对关键数据和服务器所造成的损坏。</span><span class="sxs-lookup"><span data-stu-id="1edc3-109">This section contains information about how you can design the system architecture for BizTalk Server to secure the different features in BizTalk Server, and consequently, secure the data that the servers process and store, and how to place the servers in a distributed environment that minimize the potential for critical data and servers being compromised in the event of an attack or disaster.</span></span> <span data-ttu-id="1edc3-110">本部分没有针对配置开发或测试环境提供有关建议，也没有对向生产环境中部署程序集进行详细说明。</span><span class="sxs-lookup"><span data-stu-id="1edc3-110">This section does not provide recommendations for configuring development, or test environments, or details for deploying an assembly into a production environment.</span></span> <span data-ttu-id="1edc3-111">有关部署的程序集的详细信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="1edc3-111">For more information about deploying assemblies, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1edc3-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="1edc3-112">In This Section</span></span>  
  
-   [<span data-ttu-id="1edc3-113">设计安全的体系结构</span><span class="sxs-lookup"><span data-stu-id="1edc3-113">Designing a Secure Architecture</span></span>](../core/designing-a-secure-architecture.md)  
  
-   [<span data-ttu-id="1edc3-114">设计分布式体系结构</span><span class="sxs-lookup"><span data-stu-id="1edc3-114">Designing a Distributed Architecture</span></span>](../core/designing-a-distributed-architecture.md)  
  
-   [<span data-ttu-id="1edc3-115">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="1edc3-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)