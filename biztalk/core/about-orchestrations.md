---
title: "有关业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations
- Orchestration Designer
- orchestrations, about orchestrations
- Orchestration Designer, about Orchestration Designer
ms.assetid: c0d9a3fb-da87-42cc-9e9e-e2c37232e606
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd3c1abeeb2c42c399a54aea4ba0128cc19bcd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-orchestrations"></a>有关业务流程
业务流程是用于基于 XLANG/s 语言表示可执行业务程序的灵活且功能强大的工具。 作为消息传递使用的某些表达式功能的 C# 语言，可以查看 XLANG/s。 您可以在直观的可视化绘图中设计流、解释和生成数据、调用自定义代码以及组织整个流程；并且在运行时，BizTalk 业务流程引擎执行 XLANG/s 文件（作为由 BizTalk 业务流程设计器生成的可执行业务流程）。  
  
 消息、作用于消息的发送和接收操作以及传输消息的端口都是业务流程的基本元素。 消息是业务流程与外界进行通信以及实施电子商务的媒介。  
  
 **接收**和**发送**形状封装需要接收消息发送到您的业务流程，并从其发送消息的功能。 您应熟悉业务流程设计器提供的各种形状，而这些形状表示了业务流程的逻辑流。  
  
 您应理解高级业务流程概念，例如 Web Services、相关和长期事务。 您可能无需使用所有这些功能，但了解其作用将会对您有很大帮助。  
  
 Web Services 是指接口符合 Web Services 描述语言 (WSDL) 所述标准的程序。 通过使用标准方法定义消息类型、端口、端口类型和操作，不同的系统之间可有效地进行通信。  
  
 相关是一种机制，消息利用该机制与正在运行的特定业务流程实例相关联，以便当正在运行的实例很多并且来回发送的消息也很多时，业务程序能够获得正确的信息。  
  
 使用事务可在出现意外问题时适当地维护业务流程的状态。 业务流程设计器提供不同的方法来处理异常，使您可通过可控制和可预测的方式处理错误。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [业务流程设计图面](../core/the-orchestration-design-surface.md)  
  
-   [BizTalk 业务流程选项卡工具箱](../core/biztalk-orchestrations-tab-toolbox.md)  
  
-   [业务流程开发中的步骤](../core/steps-in-orchestration-development.md)  
  
-   [有关开发业务流程的安全注意事项](../core/security-considerations-for-developing-orchestrations.md)  
  
-   [XLANG-s 语言](../core/xlang-s-language.md)  
  
-   [有关 BizTalk 业务流程引擎](../core/about-the-biztalk-orchestration-engine.md)