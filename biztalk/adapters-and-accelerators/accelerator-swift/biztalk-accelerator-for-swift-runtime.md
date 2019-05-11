---
title: BizTalk Accelerator for SWIFT 运行时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946bd3fa788f3d133e509c905e86178a94d0c5e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378892"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a>BizTalk Accelerator for SWIFT 运行时
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供了两种形式的功能： 开发材料和运行时组件。 开发材料包括 XSD 架构、 验证规则和策略和示例代码。 运行时组件包括自定义的 SWIFT 反汇编程序、 自定义的 SWIFT 汇编程序、 消息修复和新提交业务流程 (MrsrRepair.odx) 和 FIN 响应对帐业务流程 (FrrMain.odx)。 消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。 FRR 的详细信息，请参阅[FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)。  

 下图显示的高级系统体系结构[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")  

 下图说明消息 A4SWIFT 和后端应用程序之间的流动方式以及如何使用 A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR 中的窗体站点用于消息修复和新提交。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")  

 下图说明了消息 A4SWIFT 和 SWIFT 网络之间的流动方式。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")  

 您可以定义所有 A4SWIFT 组件为 BizTalk Server 应用程序组件的特定于垂直的实现。 BizTalk 加速器提供了开发和运行时功能，以加速的顶部垂直特定于 BizTalk 应用程序开发[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 因此，所有 A4SWIFT 组件 （开发或运行时） 遵守，并放入 BizTalk Server 应用程序体系结构。 A4SWIFT 安装到运行时组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为自定义组件的运行时。 编译并部署 A4SWIFT 材料后开发和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]运行时使用它们来提供 SWIFT 消息传送和自动化功能。  

 下图显示了 BizTalk server 的高级别应用程序拓扑。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")  

 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型使用 MessageBox 数据库和控制消息流入和流出 MessageBox 数据库的发布服务器订阅服务器模式。 有关 BizTalk 体系结构和应用程序设计的详细信息，请参阅 BizTalk Server 帮助。  

 A4SWIFT 应用程序模型继承[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型并向其添加特定于 SWIFT 的组件，以便与 SWIFT 相关的解决方案上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 以下列表介绍了这些特定于 A4SWIFT 的组件：  

- **运行时组件。** SWIFT 反汇编程序中的接收管道、 SWIFT 汇编程序发送管道、 消息修复和新提交业务流程和 FIN 响应对帐业务流程中。  

- **开发材料。** SWIFT 架构、 规则、 业务流程和示例项目包含在客户解决方案中并部署到执行的运行时上。  

  本部分介绍详细信息中的 A4SWIFT 运行时。  

  本部分包含：  

- [SWIFT 反汇编程序](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  

- [SWIFT 汇编程序](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  

- [通过接收位置和 InfoPath 表单提交消息](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  

- [消息验证引擎](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)
