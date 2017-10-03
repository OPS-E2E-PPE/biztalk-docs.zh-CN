---
title: "教程： 将与 Salesforce 集成 BizTalk Server 2013 |Microsoft 文档"
description: "使用服务总线和 BIzTalk Server 与 Salesforce 集成"
ms.custom: 
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8af013bc97ae9618dc19cab57d52fcb4829f0842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a>教程： 将与 Salesforce 集成 BizTalk Server 2013
审阅者： [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)， [Steef-jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引入了进行大量的混合方案涉及在本地和 Azure 技术现在可能某些新适配器。 在本教程中，我们将了解纯粹的云实体（如 Salesforce）如何使用某些新适配器和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与本地 [!INCLUDE[winazure](../includes/winazure-md.md)] 集成。 在开始之前，我们先来了解一下我们尝试通过将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 Salesforce 集成来实现的业务目标。  
  
 我们还可以创建涉及 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 Salesforce 以及以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的混合解决方案，但是，如果涉及使用 Web 服务 (SOAP) 与 Salesforce 交互，则解决方案将会更加复杂。 有了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和新适配器，解决方案将容易得多。  
  
## <a name="business-scenario"></a>业务方案  
 Northwind 使用 Salesforce 在线 CRM 系统作为其通过销售渠道跟踪客户的解决方案。 每次在 Salesforce 系统中创建一个销售机会时，Northwind 就会希望其本地系统（如 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]）收到通知，以使其他下游系统可以提取该数据并启动其他相关进程。 Northwind 计划使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供的新适配器以及添加 [!INCLUDE[winazure](../includes/winazure-md.md)] 的某些组件来实现此解决方案。 此解决方案的端到端数据流如下所示：  
  
-   销售代表在 Salesforce 系统中创建了一个“机会”。  
  
-   当该机会的状态设置为“已结束 - 赢得”时，将向 [!INCLUDE[winazure](../includes/winazure-md.md)] 上托管的中继终结点发送通知。  
  
-   使用新的 WCF-BasicHttpRelay 适配器，通知信息将传递到本地安置的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用作为通知的一部分收到的信息，通过新的 WCF-WebHttp 适配器调用 Salesforce 中的 REST 终结点，以获取有关机会的详细信息。  
  
-   最终，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用从 Salesforce 收到的信息在内部 SQL Server 数据库表中创建一个采购订单条目。  
  
 以下是为实现此解决方案中所述的集成目标必须执行的一组步骤。 其中每个步骤均涉及在继续创建解决方案时要了解的一组广泛活动。  
  
 以下是描述端到端集成解决方案的插图：  
  
 ![BizTalk Server 与 Salesforce 集成方案](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")  
  
## <a name="prerequisites"></a>先决条件  
 你必须已在要设置此解决方案的计算机上安装了以下软件：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
-   [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
-   [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
 你必须拥有以下服务订阅：  
  
-   [!INCLUDE[winazure](../includes/winazure-md.md)] 订阅  
  
-   Salesforce 开发人员版帐户  
  
## <a name="more-resources"></a>更多资源  
 除了本教程中，你还可以查看以下资源来了解有关集成的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Salesforce 使用中引入的新适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   虚拟实验室演示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Salesforce 集成位于[http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930)。  
  
-   基于本教程的示例是下载[http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [步骤 1： 创建服务总线 Namespace](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [步骤 4： 配置 BizTalk Server 解决方案](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [步骤 5： 测试解决方案](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)