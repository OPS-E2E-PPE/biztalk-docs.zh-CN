---
title: "步骤 3： 在 Visual Studio 中创建 BizTalk Server 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4da3333-e430-4caf-bc29-44a60ebac385
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 402434ec74327b55f243fecd9d1c347ce4ff0390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-the-biztalk-server-solution-in-visual-studio"></a>步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案
在本部分中，我们将了解如何创建实现以下目标的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案：从 Salesforce 接收机会通知，查询 Salesforce 以获取有关机会的更多信息，并最终将这些信息插入用户所在场所的 SQL Server 数据库。 此部分将按照其中每个更广泛的步骤进一步分类。  
  
> [!NOTE]
>  为了能够向 Salesforce 发送消息并从 Salesforce 将消息接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，我们需要向解决方案中添加一些自定义组件。 我们将创建这些自定义组件中的[步骤 3d： 启用 BizTalk Server 发送和接收来自 Salesforce](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 3a： 接收到 BizTalk Server Salesforce 机会通知](../core/step-3a-receive-salesforce-opportunity-notification-into-biztalk-server.md)  
  
-   [步骤 3b： 检索机会从 Salesforce 使用 WCF WebHttp 适配器的详细信息](../core/step-3b-retrieve-opportunities-from-salesforce-using-the-wcf-webhttp-adapter.md)  
  
-   [步骤 3c: SQL Server 数据库中插入机会详细信息](../core/step-3c-insert-opportunity-details-into-a-sql-server-database.md)  
  
-   [步骤 3d： 启用 BizTalk 服务器发送和接收来自 Salesforce 的消息](../core/step-3d-enabling-biztalk-server-to-send-and-receive-messages-from-salesforce.md)  
  
-   [步骤 3e： 生成并部署 BizTalk 服务器解决方案](../core/step-3e-build-and-deploy-the-biztalk-server-solution.md)  
  
## <a name="see-also"></a>另请参阅  
 [教程 6： 将与 Salesforce 集成 BizTalk Server 2013](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)