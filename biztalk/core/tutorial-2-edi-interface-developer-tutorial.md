---
title: '教程 2: EDI 接口开发人员教程 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb84454d2570ae6833847b598b55af6cf7777e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286941"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a>教程 2: EDI 接口开发人员教程
本教程演示如何使用接口开发人员 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 EDI 功能。  
  
 **教程方案**  
  
 在此教程中，你的贸易合作伙伴使用 ANSI X12 版本 4010 850 事务集（一条 850 消息）将采购订单发送到你的公司。 你的公司使用名为“订单系统”的内部应用程序处理采购订单。  
  
 你是一名接口开发人员，负责设计从贸易合作伙伴处收到的 850 消息与公司内部的订单系统之间的接口。 你的贸易合作伙伴要求为发送的每条 850 消息获得一个功能确认 (997)。  
  
 为了方便地进行引用，使用了以下标识符：  
  
|实体|Identifier|  
|------------|----------------|  
|你的公司|OrderSystem|  
|你的贸易合作伙伴|Fabrikam|  
  
 在完成的解决方案中，消息的流动过程如下所示：  
  
 ![EDI 接口开发人员教程消息流](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")  
  
 **消息流**  
  
 教程中的解决方案将执行以下操作：  
  
1.  接收来自贸易合作伙伴 Fabrikam 的平面文件交换。  
  
    > [!NOTE]
    >  此列表中的事件可能不会按所示顺序发生。  
  
2.  对照 EDI 交换的架构验证该交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。  
  
3.  为收到的 EDI 交换生成 997 确认，并将其放置到 MessageBox 中。  
  
4.  通过单向发送端口提取 997 XML，并组装 997 EDI 交换。  
  
5.  将 997 交换发送给 Fabrikam。  
  
6.  选取消息 XML 通过单向发送端口，并且组合 EDI 交换的消息。  
  
7.  将 EDI 交换发送给 OrderSystem。  
  
 **Configuration**  
  
 在本教程中，你将执行以下操作：  
  
-   配置 BizTalk 以期望从你的贸易合作伙伴处获得 850 消息并发回一个 997 确认  
  
-   使用 BizTalk 映射将 850 消息数据转换为订单系统所需的格式。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 教程文件中提供了此映射。  
  
-   配置用于接收 850 消息的接收端口。  
  
-   配置发送端口以正确格式发送 OrderSystem 850 消息到 OrderSystem。  
  
-   配置发送端口以订阅 BizTalk 生成的 997 确认并将其路由回贸易合作伙伴，Fabrikam。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 准备 EDI 接口开发人员教程](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [步骤 2： 更新和部署教程解决方案](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [步骤 3： 为你的组织配置方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [步骤 4： 为贸易合作伙伴配置方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [步骤 5： 配置接收端口和接收位置](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [步骤 6： 配置发送端口将数据发送到你的组织](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [步骤 7： 配置发送端口将确认发送到贸易合作伙伴](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [步骤 8： 配置参与方之间贸易合作伙伴协议](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [步骤 9： 测试 EDI 解决方案](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)