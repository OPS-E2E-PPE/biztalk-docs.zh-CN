---
title: BizTalk Server 简介 |Microsoft Docs
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
ms.openlocfilehash: 0fbccc465e64e16cc5610a18124f18099471487c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381564"
---
# <a name="introducing-biztalk-server"></a>BizTalk Server 简介
将系统关联在一起预期行为，并已成为一种规范。 随着组织逐渐面向服务的环境，真正的目标转向 — 创建合并单独的系统融为一体的有效的业务流程 — reach 中出现。  
  
 Microsoft BizTalk Server 允许连接不同的软件，然后以图形方式创建和修改使用该软件的流程逻辑。 BizTalk Server 还可以监视正在运行的进程、 与贸易合作伙伴进行交互以及执行其他面向企业的任务的信息工作者。  
  
 在 BizTalk Server 中的重要新功能包括：  
  
-   更好地支持部署、 监视和管理应用程序  
  
-   极大地简化了安装  
  
-   改进的功能的业务活动监视 (BAM)  
  
BizTalk Server 还使用其他 Microsoft 技术的最新版本。 它基于.NET Framework 中，并且在 Microsoft Visual Studio 中托管的开发人员工具。 对于存储，BizTalk Server 使用 SQL Server。 BizTalk Server 可以运行 64 位 Windows 的服务器上，以便充分利用更大的内存和硬件提供了其他权益。  
  
## <a name="what-is-biztalk-server"></a>BizTalk Server 是什么？  
 将不同的系统组合成有效的业务流程是特别棘手的问题。 相应地，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括一系列技术。 下图显示了产品的主要组件。  
  
 ![BizTalk Server 组件概述](../core/media/d167608e-7c51-4d52-b8fa-9d4149242934.gif "d167608e-7c51-4d52-b8fa-9d4149242934")  
  
 如图所示，该产品的核心是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎。 该引擎具有两个主要部分：  
  
- 消息组件，它提供一系列其他软件进行通信的功能。 通过依赖于不同类型的通信的适配器，该引擎可以支持各种协议和数据格式，包括 Web 服务和许多其他。  
  
- 支持用于创建和运行调用业务流程以图形方式定义进程。 基于该引擎的消息传送组件，业务流程实现驱动所有或部分业务流程的逻辑。  
  
  多个其他 BizTalk 组件与该引擎还使用协同包括：  
  
- 业务规则引擎的计算结果为复杂的规则集。  
  
- 使用组中心，开发人员和管理员可监视并管理该引擎在业务流程可以运行。  
  
- 企业单一登录 (SSO) 工具，提供在 Windows 和非 Windows 系统之间映射验证信息的能力。  
  
  在此基础上，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括业务活动监视，信息工作者可使用该监视正在运行的业务流程。 在业务而不是技术层面讲，显示的信息和业务用户可确定显示的信息。  
  
## <a name="connecting-diverse-systems"></a>连接不同的系统  
 绝大多数现代业务流程至少部分取决于软件。 尽管这些进程的一些单个应用程序支持，但许多其他依赖于不同的软件系统。 在许多情况下，此软件已在创建不同的时间，不同的平台，以及使用不同的技术。 自动执行这些业务流程需要连接不同的系统。  
  
 可以解决此难题就各种不同的名称： 业务流程自动化 (BPA)、 业务流程管理 (BPM) 和其他人。 该名称，无论两个方案都是最重要的应用程序集成。 一个方案用于连接单个组织，通常称为企业应用程序集成 (EAI) 中的应用程序。 其他，称为企业到企业 (B2B) 集成，连接不同组织中的应用程序。  
  
 下图显示了 BizTalk Server 引擎对 EAI 问题应用的核心的一个简单的示例。 在此方案中，可能运行在 IBM 大型机上的清单应用程序注意到项的库存不足，因此发出订购更多的项的请求。 此请求发送到 BizTalk Server 业务流程 （步骤 1），然后向此组织的 ERP 应用程序请求采购订单 （步骤 2） 发出请求的。 可能在 Unix 系统运行，ERP 应用程序发回请求的采购订单 （步骤 3） 和 BizTalk Server 业务流程接着通知执行基于的应用程序，可能是使用.NET Framework 中，应订购该项的 Windows （步骤 4）.  
  
 ![在 BizTalk 引擎中实现的 EAI。](../core/media/7d8558da-03cf-494b-8334-efe0ea15a6a7.gif "7d8558da-03cf-494b-8334-efe0ea15a6a7")  
  
 在此示例中，每个应用程序使用不同协议的通信。 因此，BizTalk Server 引擎的消息传送组件必须能够使用的本机通信样式中的每个应用程序。 另请注意没有单个应用程序会知道整个业务流程。 协调所有涉及的软件所需的智能是 BizTalk Server 业务流程中实现的。  
  
 连接组织内的应用程序很重要，但连接不同组织的应用程序可以具有更具值。 下图显示了这种类型的企业到企业集成的简单示例。 在这种情况下，在图顶部采购组织运行两个供应商组织进行交互的 BizTalk Server 业务流程。 供应商 A 也使用 BizTalk Server 中，提供对其 Supply 应用程序的间接访问。 供应商 B 使用来自另一个供应商，连接到采购组织的 BizTalk Server 业务流程使用，例如，Web 服务的集成平台。  
  
 ![企业到企业集成关系图](../core/media/b1d8787d-e842-468e-96c5-b68875d9abc3.gif "b1d8787d-e842-468e-96c5-b68875d9abc3")  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk Server](../core/understanding-biztalk-server.md)
