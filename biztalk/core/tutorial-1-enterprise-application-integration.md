---
title: 教程 1:企业应用程序集成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enterprise application integration tutorial
- getting started tutorials, integrating enterprise applications
- enterprise application integration tutorial, about the tutorial
ms.assetid: aca5fc97-0fd6-4964-9cf1-482aa4f444b8
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6abc6e3b56c0145a10392a8523700115b79c66cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279654"
---
# <a name="tutorial-1-enterprise-application-integration"></a>教程 1:企业应用程序集成
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为应用程序集成和业务流程管理 (BPM) 提供了开发和运行时环境。 本教程提供了一个端到端练习设置和部署企业应用程序集成 (EAI) 解决方案使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
##  <a name="BKMK_Tut1_scenario"></a> 业务方案  
 Contoso 是销售计算机硬件和软件的一个联机商店。  该公司最近购买的企业资源规划 (ERP) 系统来管理其资源。  在本教程中，将开发企业应用程序集成 (EAI) 解决方案使用 BizTalk Server 来集成到 ERP 系统中，现有仓库系统，并自动执行仓库请求过程。  
  
 有有关此集成解决方案的几个问题：  
  
- **消息传输**。  仓库系统和 ERP 系统可以驻留在两个不同的平台，并使用不同传输协议来发送和接收消息。 此解决方案必须能够接收使用发送系统支持的协议的消息和转发的消息使用接收系统支持的协议。  BizTalk Server 使用*适配器*消息传输。  有许多都附带有 BizTalk Server 安装和 BizTalk 适配器包的本地适配器。  如需其他适配器，可以从供应商购买或开发自己的使用适配器框架提供的 BizTalk Server。 有关适配器的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=191131 ](http://go.microsoft.com/fwlink/?LinkId=191131)。  
  
- **消息转换**。 有多种消息类型，例如，扩展标记语言 (XML)、 电子数据交换 (EDI)、 分界的文件等。 BizTalk Server 是以 XML 为中心。 在大多数情况下，可以将入站的消息转换 XML 第一次。  此过程称为*分析*。  在出站端，可以将消息从 XML 转换为其他类型。  此过程称为*序列化*。  
  
- **业务流程管理**。 大多数 EAI 方案将多个只需转发的消息从一个系统到另一个系统。  它们通常涉及多个系统和复杂的工作流。  在此方案中，仓库发送一条请求库存补货;你的解决方案接收的消息，然后检查请求的总计。  如果总计超出特定数量，解决方案会自动拒绝该请求并发送拒绝消息;否则该解决方案将请求转发到 ERP 系统。  
  
   下图说明了业务流程：  
  
   ![教程 1 消息流](../core/media/tut1-msg-flow.gif "tut1_msg_flow")  
  
  在本教程中，您使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发工具来设计和部署业务流程。  
  
## <a name="preparation"></a>准备  
 还有一些必须在创建 BizTalk Server 的集成解决方案之前收集的基本信息：  
  
-   多少应用程序/系统的 BizTalk Server 解决方案需要集成？  在此方案中，有两个系统：ERP 和仓库。  
  
-   哪种传输协议支持的每个应用程序？  若要简化此解决方案，我们假设两个应用程序使用的文件。  仓库系统删除请求作为文件文件夹中的文件。 BizTalk Server 解决方案从文件夹提取该文件，处理该文件，然后将请求放入 ERP 系统监视的另一个文件夹。  
  
-   使用什么消息类型的应用程序？  若要简化此解决方案，我们假设两个应用程序使用的 XML 类型。 BizTalk 架构是 BizTalk 消息中定义的 XML 数据结构的文档和它们的用途是创建用于处理和验证 XML 消息的模板。 BizTalk Server 附带用于创建 BizTalk 架构的 BizTalk 编辑器。  
  
-   业务流程是什么？  此标题在前面已经介绍了该过程。  
  
## <a name="biztalk-server-architecture"></a>BizTalk Server 体系结构  
 它是有助于您了解 BizTalk Server 如何运行该解决方案。  下图显示了通过的数据流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 ![教程 1 方案数据流](../core/media/tut1-dataflow.gif "Tut1_Dataflow")  
  
-   （仓库系统将请求放到文件文件夹。）  
  
-   BizTalk Server 接收位置使用文件适配器和 XML 传输管道配置。  文件适配器轮询定期从该文件夹的文件。 一旦收到一条消息，BizTalk Server 消息引擎将推送消息传递管道。  由于请求消息是 XML 格式，因此在这种情况下使用 XML 传输管道。  XML 传输管道可确保消息是格式正确的 XML 文件。  然后该消息将保存到 MessageBox 数据库。  
  
-   当业务流程引擎发现一条消息已准备好处理的业务流程时，它实例化业务流程的实例。  具体取决于消息的总计，业务流程引擎将请求消息或请求拒绝消息保存到 MessageBox 数据库。  
  
-   同样，具体取决于请求消息或请求拒绝消息，消息引擎使用的发送端口来处理该消息。  消息引擎先推送消息传递 XML 传输管道，，然后使用文件适配器将消息发送到发送端口配置基于不同的文件文件夹。  
  
-   （仓库系统和 ERP 系统监视指定的文件夹以获取消息。）  
  
## <a name="in-this-section"></a>本节内容  
  
-   [开始学习教程之前](../core/before-you-begin-the-tutorial.md) 
  
-   [第 1 课：定义架构和映射](../core/lesson-1-define-schemas-and-a-map.md) 
  
-   [第 2 课：定义业务流程](../core/lesson-2-define-the-business-process.md)  
  
-   [第 3 课：部署解决方案](../core/lesson-3-deploy-the-solution.md)