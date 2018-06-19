---
title: 引入了 BizTalk Server |Microsoft 文档
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06a4a31a-eefe-4b1b-89ca-2cba2b6fa587
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4de6778bef644dc7bbfa25b46c28b36e1741ba6f
ms.sourcegitcommit: d0a1816a8dd8412906245d40c6479b08d7b3b20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
ms.locfileid: "28910101"
---
# <a name="introducing-biztalk-server"></a>BizTalk Server 简介
将系统在一起预期行为，并且变得范数。 随着组织逐渐转向面向服务的环境，其现实目标也即将实现，即创建将各种单独的系统融为一体的有效业务流程。  
  
 Microsoft BizTalk Server 可允许连接不同软件，然后以图形方式创建和修改过程逻辑，它使用该软件。 使用 BizTalk Server，信息工作者还可以监视正在运行的进程、与贸易合作伙伴进行交互，以及执行其他面向企业的任务。  
  
 BizTalk Server 的主要新增功能包括：  
  
-   更好地支持部署、监视和管理应用程序  
  
-   极大地简化了安装  
  
-   改进了业务活动监视 (BAM) 功能  
  
BizTalk Server 还使用了其他 Microsoft 技术的最新版本。 它构建在.NET Framework 中，且在 Microsoft Visual Studio 中托管的开发人员工具。 对于存储，BizTalk Server 使用 SQL Server。 BizTalk 服务器可以运行在 64 位 Windows 服务器上利用更大的内存和硬件提供其他好处。  
  
## <a name="what-is-biztalk-server"></a>BizTalk Server 概述  
 将不同的系统组合到有效的业务流程中，解决这一问题可能相当困难。 因此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含一系列技术。 下图显示了该产品的主要组件：  
  
 ![BizTalk 服务器组件概述](../core/media/d167608e-7c51-4d52-b8fa-9d4149242934.gif "d167608e-7c51-4d52-b8fa-9d4149242934")  
  
 如上图所示，该产品的核心是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎。 该引擎由两个主要部分组成：  
  
-   消息传送组件，提供与其他一系列软件进行通信的功能。 通过依靠于不同通信类型的适配器，该引擎可以支持诸如 Web Services 之类的各种协议和数据格式。  
  
-   支持创建和运行以图形方式定义的进程（称为业务流程）。 业务流程建立在该引擎的消息传送组件之上，可实现驱动所有或部分业务流程的逻辑。  
  
 某些其他 BizTalk 组件也可以与该引擎协同使用，包括：  
  
-   业务规则引擎，用于对复杂的规则集进行评估。  
  
-   使用组中心，开发人员和管理员可监视并管理该引擎及其运行的业务流程。  
  
-   企业单一登录 (SSO) 工具，提供在 Windows 系统与非 Windows 系统之间映射验证信息的功能。  
  
 在此基础上，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括业务活动监视，信息工作者可使用该技术来监视正在运行的业务流程。 信息以业务术语显示，而不是以技术术语显示，并且业务用户可确定要显示的信息。  
  
## <a name="connecting-diverse-systems"></a>将不同的系统连接  
 绝大多数现代业务流程都或多或少地依赖于软件。 尽管其中部分流程仅由单个应用程序提供支持，但其他许多业务流程都依赖于不同的软件系统。 在许多情况下，已使用不同的技术在不同时间、不同平台上创建了此软件。 若要使这些业务流程实现自动化，则需要连接不同的系统。  
  
 各种名称积极应对这些挑战就︰ 业务流程自动化 (BPA)、 业务流程管理 (BPM) 及其他类型。 不管名称如何，这两个方案对于应用程序集成都至关重要。 一个方案用于连接单个组织内的应用程序，通常称为企业应用程序集成 (EAI)。 另一个方案称为企业对企业 (B2B) 集成，用于连接不同组织中的应用程序。  
  
 下图显示了对 EAI 问题应用核心 BizTalk Server 引擎的一个简单示例。 在此方案中，库存应用程序（假设其在 IBM 大型机上运行）注意到某项的库存不足，因此发出订购更多该项的请求。 此请求将发送到某个 BizTalk Server 业务流程（步骤 1），该业务流程随后向此组织的 ERP 应用程序发出请求，以请求采购订单（步骤 2）。 该 ERP 应用程序（假设其在 Unix 系统上运行）将发送回所请求的采购订单（步骤 3），然后 BizTalk Server 业务流程将通知实现应用程序（假设其使用 .NET Framewor 基于 Windows 构建）应订购该项（步骤 4）。  
  
 ![EAI BizTalk 引擎中实现。](../core/media/7d8558da-03cf-494b-8334-efe0ea15a6a7.gif "7d8558da-03cf-494b-8334-efe0ea15a6a7")  
  
 在此示例中，每个应用程序均使用不同的协议进行通信。 因此，BizTalk Server 引擎的消息传送组件必须能够使用各应用程序固有的通信方式与其进行通信。 此外，请注意，没有任何单个应用程序会知道整个业务流程。 BizTalk Server 业务流程实现了协调所有涉及的软件所需的智能。  
  
 连接组织内的各个应用程序固然重要，但连接不同组织的应用程序有时更具价值。 下图显示了此类企业对企业集成的一个简单示例。 在此案例中，位于图形顶部的采购组织将运行与两个供应商组织进行交互的 BizTalk Server 业务流程。 供应商 A 也使用 BizTalk Server，因此可提供对其 Supply 应用程序的间接访问。 供应商 B 使用来自另一个供应商的集成平台，可使用 Web Services 之类的工具连接到采购组织的 BizTalk Server 业务流程。  
  
 ![企业到企业集成关系图](../core/media/b1d8787d-e842-468e-96c5-b68875d9abc3.gif "b1d8787d-e842-468e-96c5-b68875d9abc3")  
  
## <a name="see-also"></a>另请参阅  
 [了解 BizTalk Server](../core/understanding-biztalk-server.md)
