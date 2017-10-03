---
title: "BizTalk Accelerator for SWIFT 运行时 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- developing, components
- architecture, topology
- messages, message flow diagram
- runtime, components
- SWIFT runtime
- architecture, runtime architecture
- SWIFT network
- A4SWIFT, network
- topology
ms.assetid: c0f59760-7d7d-4b22-a7dc-54e563971d4a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312a91d403d125fe6d245b92bf83da57d1031fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-accelerator-for-swift-runtime"></a>BizTalk Accelerator for SWIFT 运行时
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]在两种形式提供的功能： 开发材料和运行时组件。 开发资料包括 XSD 架构，验证规则和策略，以及示例代码。 运行时组件包括自定义 SWIFT 反汇编程序、 自定义 SWIFT 汇编程序、 消息修复和新提交业务流程 (MrsrRepair.odx) 和 FIN 响应对帐业务流程 (FrrMain.odx)。 有关消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。 FRR 的详细信息，请参阅[FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)。  
  
 下图显示了高级系统体系结构[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  
  
 下图说明如何将消息流之间 A4SWIFT 和后端应用程序，以及如何 A4SWIFT 使用[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]MRSR 中的窗体站点消息修复和新的提交。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  
  
 下图说明了消息 A4SWIFT 和 SWIFT 网络之间的流动方式。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  
  
 你可以定义所有 A4SWIFT 组件为垂直特定实现[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]应用程序组件。 BizTalk 加速器提供开发和运行时功能，以加速垂直特定 BizTalk 应用程序开发的顶部[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 因此，所有 A4SWIFT 组件 （开发或运行时） 遵守，并且适合，[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]应用程序体系结构。 A4SWIFT 安装运行时组件都进入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为自定义组件的运行时。 编译并部署，A4SWIFT 材料后开发和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]运行时使用它们来提供消息传送和自动化功能的 SWIFT。  
  
 下图显示的高级应用程序拓扑[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型使用 MessageBox 数据库和控制消息流执行和跳出执行 MessageBox 数据库的发布服务器订阅服务器模式。 有关 BizTalk 体系结构和应用程序设计的详细信息，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
 A4SWIFT 应用程序模型继承[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型并向其中添加 SWIFT 特定组件，用于改进 SWIFT 相关解决方案，在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 以下列表介绍了这些 A4SWIFT 特定组件：  
  
-   **运行时组件。** 接收管道、 发送管道、 消息修复和新提交业务流程和 FIN 响应对帐业务流程中的 SWIFT 汇编程序 SWIFT 反汇编程序。  
  
-   **开发材料。** SWIFT 架构、 规则、 业务流程和示例项目以在客户解决方案中包含与部署到的运行时执行。  
  
 本部分介绍详细信息中的 A4SWIFT 运行时。  
  
 本部分包含：  
  
-   [SWIFT 反汇编程序](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  
  
-   [SWIFT 汇编程序](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  
  
-   [通过提交消息接收位置和 InfoPath 窗体](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  
  
-   [消息验证引擎](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)