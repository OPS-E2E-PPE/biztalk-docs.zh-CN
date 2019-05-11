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
ms.openlocfilehash: 2fef92690d569c36d5799e027090fcf4fa9a0f98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298820"
---
# <a name="the-biztalk-server-messaging-engine"></a>BizTalk Server 消息引擎
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎，用户可以创建跨越多个应用程序通过提供两个主要操作的业务流程：  
  
- 一种方法来指定和实现驱动该业务流程的逻辑  
  
- 进行通信的应用程序之间的业务流程使用的机制  
  
  下图说明了解决这两个问题的主要引擎组件。  
  
  ![](../core/media/understandingbts-04-engine4.gif "UnderstandingBTS_04_Engine4")  
  
  如图所示，通过接收消息**接收适配器**。 不同适配器提供不同通信机制，因此可能通过访问 Web 服务，获取一条消息从一个文件，或以其他方式读取。 然后通过处理该消息**接收管道**。 此管道可以包含各种组件，用于执行将消息从其本机格式转换为 XML 文档时，验证消息的数字签名，和的详细信息等。 该消息会传送到名为的数据库**MessageBox**，这实现使用 Microsoft SQL Server。  
  
  驱动业务流程的逻辑实现为一个或多个**业务流程**，其中每个可执行代码组成。 但是在 C# 等语言中编写代码将不创建这些业务流程。 相反，业务分析员或 （更有可能） 开发人员使用适当的工具来以图形方式组织一组定义的形状来表示条件、 循环和其他行为。 可以选择使用业务流程**业务规则引擎**，其中提供了更简单并且更多轻松修改的方式来表达复杂的业务流程中的规则集。  
  
  每个业务流程将创建**订阅**以指示它想要接收的消息的类型。 相应的消息送达 MessageBox 后，会将该消息分派到其目标业务流程，采用业务过程所需的任何操作。 此处理的结果是通常是另一消息，由业务流程生成并保存在 MessageBox 中。 此消息又会处理由**发送管道**，这可能会将其从使用的内部 XML 格式转换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到其目标所需的格式、 添加数字签名，等等。 然后，消息将发送出使用**发送适配器**，它使用适当的机制与此消息的目标为其应用程序进行通信。  
  
  完整**解决方案**基于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎可以包含以下各个部分 （有时称作项目）： 业务流程、 管道、 消息架构和的详细信息。 这些部件或项目，都可以得到与作为单个单元，称为**BizTalk 应用程序**。 BizTalk 应用程序包装到单个逻辑单元，使其用于管理和部署的基本抽象解决方案所需的段。  
  
  不同的用户执行不同功能使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎。 一个**业务分析师**，例如，可以定义的规则和构成业务流程的行为。 她还确定了业务流程流定义哪些信息发送到每个应用程序和业务文档映射到另一个的方式。 业务分析员定义此过程中后,**开发人员**可以创建 BizTalk 应用程序实现它。 这包括以下任务： 定义将使用的业务文档的 XML 架构、 指定它们之间的详细的映射和创建业务流程实现该过程所需。 **管理员**还通过设置各部分之间的通信、 适当的可伸缩方式部署 BizTalk 应用程序并执行其他任务中发挥着重要作用。 所有三个角色，业务分析员，开发人员和管理员-创建并维护需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [连接系统](../core/connecting-systems.md)  
  
-   [定义业务流程](../core/defining-business-processes.md)  
  
-   [管理和监视](../core/management-and-monitoring.md)  
  
-   [企业单一登录](../core/enterprise-single-sign-on-sso.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 体系结构](../core/biztalk-server-architecture.md)   
 [运行时体系结构](../core/runtime-architecture.md)