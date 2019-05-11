---
title: 教程：将 BizTalk Server 2013 与 Salesforce 集成 |Microsoft Docs
description: 使用服务总线和 BIzTalk Server 将与 Salesforce 集成
ms.custom: ''
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2757c2a36c86bb302859f0174e8c53b5bb397025
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399163"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a>教程：将 BizTalk Server 2013 与 Salesforce 集成
审阅者：[Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)， [、 Jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引入了多大的混合方案，在本地和 Azure 技术现在可能涉及某些新适配器。 在本教程中，我们将了解如何将集成纯粹的云实体等 Salesforce 与本地集成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用某些新适配器和[!INCLUDE[winazure](../includes/winazure-md.md)]。 在开始之前，让我们了解我们尝试通过将集成来实现业务目标[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Salesforce。  
  
 我们还可以创建混合解决方案涉及[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Salesforce 以及以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，但该解决方案会复杂得多，通过使用 Web 服务 (SOAP) 涉及与 Salesforce 交互。 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和新适配器，该解决方案是这么简单。  
  
## <a name="business-scenario"></a>业务方案  
 用于跟踪通过销售渠道的客户，Northwind 使用 Salesforce 在线 CRM 系统作为其解决方案。 每次在 Salesforce 系统中创建销售机会时，Northwind 希望其在本地系统，如[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 通知，以便其他下游系统可以提取该数据并启动其他相关进程。 Northwind 计划实施该解决方案使用适用于新的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以及添加的某些组件[!INCLUDE[winazure](../includes/winazure-md.md)]。 这是如何的端到端数据流如下所示的解决方案：  
  
- 销售代表在 Salesforce 系统中创建一个"机会"。  
  
- 当该机会的状态设置为"已结束-赢得"时上, 托管的中继终结点发送通知[!INCLUDE[winazure](../includes/winazure-md.md)]。  
  
- 使用新的 Wcf-basichttprelay 适配器，通知信息传递给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]本地安置的系统。  
  
- 使用作为通知的一部分收到的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]调用 REST 终结点在 Salesforce 中，使用新的 Wcf-webhttp 适配器，以获取有关机会的详细信息。  
  
- 最后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从 Salesforce 收到的信息用于内部 SQL Server 数据库表中创建一个采购订单条目。  
  
  它们是为实现此解决方案中所述的集成目标必须执行的步骤的组。 每个步骤涉及到广泛的活动，我们将在继续创建解决方案。  
  
  下面是描述端到端集成解决方案的图例：  
  
  ![BizTalk Server 与 Salesforce 集成方案](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")  
  
## <a name="prerequisites"></a>先决条件  
 必须已在其中设置此解决方案的计算机上安装以下软件：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
- [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
- [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
  你必须拥有以下服务订阅：  
  
- 一个[!INCLUDE[winazure](../includes/winazure-md.md)]订阅  
  
- Salesforce 开发人员版帐户  
  
## <a name="more-resources"></a>更多资源  
 除了本教程中，您还可以查看以下资源，了解有关集成的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Salesforce 中引入的新适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- 虚拟实验室演示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Salesforce 集成网址[ http://go.microsoft.com/fwlink/?LinkId=290930 ](http://go.microsoft.com/fwlink/?LinkId=290930)。  
  
- 基于本教程的示例是可在下载[ http://go.microsoft.com/fwlink/?LinkId=290932 ](http://go.microsoft.com/fwlink/?LinkId=290932)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [步骤 1：创建服务总线 Namespace](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [步骤 2：设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [步骤 3：在 Visual Studio 中创建的 BizTalk Server 解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [步骤 4：配置 BizTalk Server 解决方案](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [步骤 5：测试解决方案](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)