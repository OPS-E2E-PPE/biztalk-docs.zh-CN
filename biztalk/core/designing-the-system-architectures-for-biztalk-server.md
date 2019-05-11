---
title: 为 BizTalk Server 设计系统体系结构 |Microsoft Docs
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
ms.openlocfilehash: 7e201f408303ef5a45d512bfbdcafda4c4732a73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351687"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a><span data-ttu-id="614bb-102">为 BizTalk Server 设计系统体系结构</span><span class="sxs-lookup"><span data-stu-id="614bb-102">Designing the System Architectures for BizTalk Server</span></span>
<span data-ttu-id="614bb-103">Microsoft® BizTalk® Server 部署的安全、 性能、 可用性和操作要求都高度依赖于你的业务需求、 要求、 合作伙伴、 公司规模等。</span><span class="sxs-lookup"><span data-stu-id="614bb-103">The requirements of your Microsoft® BizTalk® Server deployment for security, performance, availability, and operation are highly dependent on your business needs, requirements, partners, company size, and so on.</span></span> <span data-ttu-id="614bb-104">本部分中有关如何配置中的不同 BizTalk Server 功能时很难与典型的 BizTalk Server 组件的单个配置，并提供它的说明性指南，提供指导和建议用于大型企业在生产环境的分布式、 安全配置。</span><span class="sxs-lookup"><span data-stu-id="614bb-104">While it is difficult to consider any single configuration of BizTalk Server components as typical and provide prescriptive guidance for it, this section provides guidance and recommendations on how to configure the different BizTalk Server features in a distributed, secure configuration for the production environment of a large enterprise.</span></span>  
  
 <span data-ttu-id="614bb-105">本部分中介绍的体系结构旨在为您提供有关在其中您考虑到考虑深层防御的高度分布式环境中部署 BizTalk Server 的参考信息。</span><span class="sxs-lookup"><span data-stu-id="614bb-105">The architectures presented in this section aim to provide you with reference information about deploying BizTalk Server in a highly distributed environment where you take into consideration defense in depth.</span></span> <span data-ttu-id="614bb-106">BizTalk Server 的每个应用程序很可能具有其自己独特的安全要求根据问题领域、 所使用的协议，并在运行特定环境解决方案。</span><span class="sxs-lookup"><span data-stu-id="614bb-106">Every application for BizTalk Server is likely to have its own unique set of security requirements based on the problem domain, the protocols used, and the particular environment the solution operates in.</span></span> <span data-ttu-id="614bb-107">性能、 可用性和成本因素也会进一步影响这些要求。</span><span class="sxs-lookup"><span data-stu-id="614bb-107">Performance, availability, and cost considerations further influence these requirements.</span></span> <span data-ttu-id="614bb-108">应使用这些体系结构和本文档中的建议作为构建基块创建您自己根据需求、 威胁和您的公司资产量身定制的 BizTalk Server 部署。</span><span class="sxs-lookup"><span data-stu-id="614bb-108">You should use these architectures and the recommendations within this document as the building blocks to create your own BizTalk Server deployment tailored to the needs, threats and assets of your company.</span></span>  
  
 <span data-ttu-id="614bb-109">本部分包含有关如何设计 BizTalk 服务器以便保护 BizTalk Server 中的不同功能的系统体系结构并因此，保护数据的服务器处理和存储，以及如何将放置在服务器的信息分布式的环境中的最小化对关键数据和服务器发生攻击或灾难时遭到入侵的可能性。</span><span class="sxs-lookup"><span data-stu-id="614bb-109">This section contains information about how you can design the system architecture for BizTalk Server to secure the different features in BizTalk Server, and consequently, secure the data that the servers process and store, and how to place the servers in a distributed environment that minimize the potential for critical data and servers being compromised in the event of an attack or disaster.</span></span> <span data-ttu-id="614bb-110">本部分中并未提供建议以配置开发或测试环境中或部署到生产环境中的程序集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="614bb-110">This section does not provide recommendations for configuring development, or test environments, or details for deploying an assembly into a production environment.</span></span> <span data-ttu-id="614bb-111">有关部署程序集的详细信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。</span><span class="sxs-lookup"><span data-stu-id="614bb-111">For more information about deploying assemblies, see [Understanding BizTalk Application Deployment and Management](../core/understanding-biztalk-application-deployment-and-management.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="614bb-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="614bb-112">In This Section</span></span>  
  
-   [<span data-ttu-id="614bb-113">设计安全的体系结构</span><span class="sxs-lookup"><span data-stu-id="614bb-113">Designing a Secure Architecture</span></span>](../core/designing-a-secure-architecture.md)  
  
-   [<span data-ttu-id="614bb-114">设计分布式体系结构</span><span class="sxs-lookup"><span data-stu-id="614bb-114">Designing a Distributed Architecture</span></span>](../core/designing-a-distributed-architecture.md)  
  
-   [<span data-ttu-id="614bb-115">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="614bb-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)