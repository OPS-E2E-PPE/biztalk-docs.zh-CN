---
title: BizTalk Server 消息引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0c8d3e6-953d-4a04-adfc-b77ef7173464
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69b6cad3361c8da1fad730026e884e19003d66ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009814"
---
# <a name="the-biztalk-server-messaging-engine"></a>BizTalk Server 消息引擎
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 消息引擎提供了以下两个主要功能，用户使用这两个功能可以创建涉及多个应用程序的业务流程：  
  
- 指定和实现驱动该业务流程的逻辑的方法  
  
- 在业务流程使用的应用程序之间进行通信的机制  
  
  下图显示了解决这两个问题的主要引擎组件。  
  
  ![](../core/media/understandingbts-04-engine4.gif "UnderstandingBTS_04_Engine4")  
  
  如图所示，通过接收消息**接收适配器**。 不同适配器提供不同通信机制，所以可能会通过访问 Web Services、读取文件或其他某种方法来获取消息。 然后通过处理该消息**接收管道**。 此管道可以包含各种组件，用于执行不同的任务，例如，将消息从本机格式转换为 XML 文档、验证消息的数字签名等。 该消息会传送到名为的数据库**MessageBox**，这实现使用 Microsoft SQL Server。  
  
  驱动业务流程的逻辑实现为一个或多个**业务流程**，其中每个可执行代码组成。 但是，这些业务流程并不是通过 C# 之类的语言以编写代码的方式创建的。 实际上，业务分析员或开发人员（更可能是后者）会使用相应的工具，以图形形式将一组定义的形状组织起来以表示条件、循环及其他行为。 可以选择使用业务流程**业务规则引擎**，其中提供了更简单并且更多轻松修改的方式来表达复杂的业务流程中的规则集。  
  
  每个业务流程将创建**订阅**以指示它想要接收的消息的类型。 在相应的消息送达 MessageBox 后，会将该消息分派到其目标业务流程，后者将执行业务流程要求的任意操作。 经过此处理，通常会由业务流程生成另一个消息，并将该消息保存在 MessageBox 中。 此消息又会处理由**发送管道**，这可能会将其从使用的内部 XML 格式转换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到其目标所需的格式、 添加数字签名，等等。 然后，消息将发送出使用**发送适配器**，它使用适当的机制与此消息的目标为其应用程序进行通信。  
  
  完整**解决方案**基于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎可以包含以下各个部分 （有时称作项目）： 业务流程、 管道、 消息架构和的详细信息。 这些部件或项目，都可以得到与作为单个单元，称为**BizTalk 应用程序**。 BizTalk 应用程序将解决方案所需的所有部分包装到单独的逻辑单元，并将其用作管理和部署的基本概念。  
  
  不同的用户可能使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎执行不同功能。 一个**业务分析师**，例如，可以定义的规则和构成业务流程的行为。 还可能会确定业务流程的流程，定义要发送到每个应用程序的信息，以及如何在业务文档之间建立映射。 业务分析员定义此过程中后,**开发人员**可以创建 BizTalk 应用程序实现它。 这包括以下任务：定义将使用的业务文档的 XML 架构、指定这些架构间的详细映射，以及创建实现上述流程所需的业务流程。 **管理员**还通过设置各部分之间的通信、 适当的可伸缩方式部署 BizTalk 应用程序并执行其他任务中发挥着重要作用。 对于创建和维护 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案，以上全部三种角色（业务分析员，开发人员和管理员）都必不可少。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [连接系统](../core/connecting-systems.md)  
  
-   [定义业务流程](../core/defining-business-processes.md)  
  
-   [管理和监视](../core/management-and-monitoring.md)  
  
-   [企业单一登录](../core/enterprise-single-sign-on-sso.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 体系结构](../core/biztalk-server-architecture.md)   
 [运行时体系结构](../core/runtime-architecture.md)