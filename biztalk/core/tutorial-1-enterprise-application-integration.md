---
title: "教程 1： 企业应用程序集成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial
- getting started tutorials, integrating enterprise applications
- enterprise application integration tutorial, about the tutorial
ms.assetid: aca5fc97-0fd6-4964-9cf1-482aa4f444b8
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6ddbd6c2a3e25619c684036eee3fb0fa46a18f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-enterprise-application-integration"></a>教程 1：企业应用程序集成
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为应用程序集成和业务流程管理 (BPM) 提供了开发和运行时环境。 本教程为使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置和部署企业应用程序集成 (EAI) 解决方案提供了一个端到端的练习。  
  
##  <a name="BKMK_Tut1_scenario"></a>业务方案  
 Contoso 是销售计算机硬件和软件的在线商店。  该公司最近购买的企业资源规划 (ERP) 系统，以管理其资源。  在本教程中，将开发企业应用程序集成 (EAI) 解决方案使用 BizTalk Server 来集成到 ERP 系统中，现有仓库系统，并自动执行仓库请求过程。  
  
 有此集成解决方案的多个难题：  
  
-   **消息传输**。  仓库系统和 ERP 系统可能驻留在两个不同的平台，并用于发送和接收消息的不同传输协议。 此解决方案必须能够接收使用发送系统支持的协议的消息和转发的消息使用接收系统支持的协议。  BizTalk Server 使用*适配器*消息传输。  有许多都附带有 BizTalk Server 安装和 BizTalk 适配器包的本机适配器。  如需其他适配器，您可以从供应商处购买，也可以使用 BizTalk Server 提供的适配器框架自己开发。 有关适配器的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=191131](http://go.microsoft.com/fwlink/?LinkId=191131)。  
  
-   **消息转换**。 存在多种消息类型，如可扩展标记语言 (XML)、电子数据交换 (EDI)、分界文件等。 BizTalk Server 以 XML 为中心。 在大多数情况下，您会先将入站消息转换为 XML。  此过程称为*分析*。  在出站方，您可以将消息从 XML 转换为其他类型。  此过程称为*序列化*。  
  
-   **业务进程管理**。 大多数 EAI 方案都不是只将消息从一个系统转发到另一个系统。  它们通常涉及多个系统和复杂的工作流。  在这种情况下，仓库将发送一条请求库存补货的消息；您的解决方案将接收该消息，然后检查请求的总计。  如果总计超出特定数量，则解决方案将自动拒绝该请求并发送一条拒绝消息；否则解决方案会将请求转发到 ERP 系统。  
  
     下图对此业务流程进行了说明：  
  
     ![教程 1 消息流](../core/media/tut1-msg-flow.gif "tut1_msg_flow")  
  
 在本教程中，您将使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发工具来设计和部署业务流程。  
  
## <a name="preparation"></a>准备  
 在创建 BizTalk Server 集成解决方案之前，您必须收集一些基本信息：  
  
-   BizTalk Server 解决方案需要集成多少应用程序/系统？  在本方案中有两个系统：ERP 系统和仓库系统。  
  
-   每个应用程序支持哪种传输协议？  为简化此解决方案，我们假设两个应用程序都使用文件。  仓库系统将请求作为文件放入文件夹。 BizTalk Server 解决方案从该文件夹提取此文件，再处理此文件，然后将请求放入 ERP 系统监视的另一个文件夹。  
  
-   应用程序使用什么消息类型？  为简化此解决方案，我们假设两个应用程序都使用 XML 类型。 BizTalk 架构是一些定义 BizTalk 消息中 XML 数据结构的文档，其目的是创建用于处理和验证 XML 消息的模板。 BizTalk Server 附带用于创建 BizTalk 架构的 BizTalk 编辑器。  
  
-   业务流程是什么？  在本文的前面部分已经介绍了该流程。  
  
## <a name="biztalk-server-architecture"></a>BizTalk Server 体系结构  
 这对于理解 BizTalk Server 如何运行解决方案十分有用。  下图显示了通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的数据流。  
  
 ![教程 1 方案数据流](../core/media/tut1-dataflow.gif "Tut1_Dataflow")  
  
-   （仓库系统将请求放入文件夹。）  
  
-   BizTalk Server 接收位置通过文件适配器和 XML 传输管道进行配置。  文件适配器定期从文件夹轮询文件。 收到消息后，BizTalk Server 消息引擎将通过管道推送该消息。  由于请求消息是 XML 格式，因此在这种情况下使用 XML 传输管道。  XML 传输管道将确保该消息是格式正确的 XML 文件。  然后，该消息将保存到 MessageBox 数据库。  
  
-   业务流程引擎发现某条消息已准备好供业务流程处理时，它将实例化该业务流程的实例。  业务流程引擎会将请求消息或请求拒绝消息保存到 MessageBox 数据库，具体取决于消息的总计。  
  
-   同样，根据是请求消息还是请求拒绝消息，消息引擎将使用任一发送端口处理该消息。  消息引擎先通过 XML 传输管道推送该消息，然后根据发送端口配置，使用文件适配器将该消息发送到不同的文件夹。  
  
-   （仓库系统和 ERP 系统都会监视指定的文件夹以获取消息。）  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在开始本教程之前](../core/before-you-begin-the-tutorial.md) 
  
-   [第 1 课： 定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md) 
  
-   [第 2 课： 定义的业务流程](../core/lesson-2-define-the-business-process.md)  
  
-   [第 3 课： 部署解决方案](../core/lesson-3-deploy-the-solution.md)