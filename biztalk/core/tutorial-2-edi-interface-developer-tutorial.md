---
title: 教程 2:EDI 接口开发人员教程 |Microsoft Docs
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
ms.openlocfilehash: c1af388c62be4e23ba13d29f93567cdab76fdfb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401726"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a>教程 2:EDI 接口开发人员教程
本教程演示如何使用中的 EDI 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中接口开发人员。  
  
 **教程方案**  
  
 在此方案中，您的贸易合作伙伴将采购订单发送到你的公司使用 ANSI X12 版本 4010 850 事务集 （条 850 消息）。 你的公司使用的内部应用程序，订单系统，以处理采购订单。  
  
 你是负责设计从贸易合作伙伴收到的 850 消息与公司的内部订单系统之间的接口的接口开发。 您的贸易合作伙伴要求为发送每条 850 消息功能确认 (997)。  
  
 为了方便引用，使用以下标识符：  
  
|实体|Identifier|  
|------------|----------------|  
|你的公司|OrderSystem|  
|您的贸易合作伙伴|Fabrikam|  
  
 已完成的解决方案中的消息流将如下所示：  
  
 ![EDI 接口开发人员教程消息流](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")  
  
 **消息流**  
  
 本教程中的解决方案将执行以下操作：  
  
1. 接收来自贸易合作伙伴 Fabrikam 的平面文件交换。  
  
   > [!NOTE]
   >  显示的顺序可能不是此列表中的事件。  
  
2. 验证针对其架构的 EDI 交换，将消息拆装成 XML，并将消息 XML 放置到 MessageBox 中。  
  
3. 生成一个 997 确认已接收的 EDI 交换，并放置到 MessageBox 中。  
  
4. 提取 997 XML 通过单向发送端口，并组装 997 EDI 交换。  
  
5. 将 997 交换发送至 Fabrikam。  
  
6. 提取消息 XML 通过单向发送端口，并组装消息 EDI 交换。  
  
7. 将 EDI 交换发送到 OrderSystem。  
  
   **Configuration**  
  
   在本教程中，你将执行以下操作：  
  
- 配置 BizTalk 期望来自您的贸易合作伙伴的 850 消息，并要发回一个 997 确认。  
  
- 使用 BizTalk 映射将 850 消息数据转换为订单系统所需的格式。 在教程文件中提供了此映射[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK。  
  
- 配置用于接收 850 消息的接收端口。  
  
- 配置发送端口以发送到 OrderSystem 850 消息，以正确的格式。  
  
- 配置发送端口以订阅 BizTalk 生成 997 确认路由回贸易合作伙伴 Fabrikam。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：EDI 接口开发人员教程的准备工作](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [步骤 2：更新和部署教程解决方案](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [步骤 3：为你的组织配置参与方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [步骤 4：为您的贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [步骤 5：配置接收端口和接收位置](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [步骤 6：配置发送端口以将数据发送到你的组织](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [步骤 7：配置用于向贸易合作伙伴发送确认的发送端口](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [步骤 8：配置参与方之间的贸易合作伙伴协议](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [步骤 9：测试 EDI 解决方案](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)