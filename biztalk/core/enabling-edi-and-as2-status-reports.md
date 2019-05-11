---
title: 启用 EDI 和 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa40fbad-51ad-40e0-9fe3-68e54beb11a5
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b06ae5e1fde570a9c27c1951a4eca7a7c5481e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349904"
---
# <a name="enabling-edi-and-as2-status-reports"></a>启用 EDI 和 AS2 状态报告
本主题介绍如何配置 EDI 和 AS2 状态报告中的**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 在下面的过程中选择状态报告跟踪数据存储在 BizTalk 跟踪数据库 (BizTalkDTADb) 根据存储属性。 你可以配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]启用状态报告为每个协议。 根据存储的数据量，应定期存档活动存储中的数据和存档存储，根据最终清理。 有关管理 BizTalkDTADb 数据库的详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。  
  
 您可以启用以下三种方式的状态报告：  
  
- 对于入站或出站 EDI 交换解析为协议启用状态报告。  
  
- 启用对 EDI 备用协议属性的状态报告以便 EDI 交换激活状态报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议。  
  
- 启用 AS2 消息的状态报告。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组或 BizTalk Server B2B Operators 组。  
  
### <a name="to-enable-edi-status-reports-for-an-agreement"></a>为协议启用 EDI 状态报告  
  
1. 在中**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**控制台中，单击**方**节点下的[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点。  
  
2. 在中**参与方和业务配置文件**窗格中，单击包含你想要启用状态报告的 X12 或 EDIFACT 协议的参与方。  
  
3. 在中**协议**部分中，右键单击你想要启用状态报告，然后单击的协议**属性**。  
  
4. 在中**常规**选项卡上，在**公用主机设置**部分中，单击**打开报告**。  
  
   > [!NOTE]
   >  此步骤会导致消息条目进入状态报告 UI 中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
5. 选择**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。  
  
   > [!NOTE]
   >  如果您启用的事务集存储在激活批处理业务流程实例，将不存储创建的批的事务集。 但是，如果您禁用事务集存储在激活批处理业务流程实例，将在批处理过程禁用存储。  
  
6. 单击“确定” 。  
  
7. 重新启动 BizTalk 服务 （在计算机管理对话框中）。 如果你的解决方案中正在使用 AS2EdiReceive 管道或 AS2EdiSend 管道，重新启动 IIS Admin 服务 (使用*iisreset*命令)，因此也。  
  
   > [!NOTE]
   >  BizTalk 服务需要重新启动后 EDI 状态报告已激活或停用的更改才能生效。 如果你的解决方案中使用 AS2EdiReceive 或 AS2EdiSend 管道，BizTalk 服务和 IIS 服务需要更改才能生效，必须重新启动。 请注意，这不是必要时启用 AS2 状态报告。  
  
### <a name="to-enable-edi-status-reports-for-fallback-agreements"></a>为备用协议启用 EDI 状态报告  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**节点，右键单击**参与方**，然后选择**X12 后备设置**或**EDIFACT 后备设置**。  
  
   > [!NOTE]
   >  当在备用协议中配置状态报告时，配置仅适用于任何协议确定消息。  
  
2. 在中**回退设置常规页**选项卡上，单击**激活 EDI 报告**。  
  
   > [!NOTE]
   >  此步骤会导致消息条目进入状态报告 UI 中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
3. 选择**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。  
  
   > [!NOTE]
   >  **对于 EDIFACT 编码的消息**:如果选择此属性，还必须在 EDI 全局属性对话框中的 UNB 段定义页中选择 UNB3.2 字段 （代码限定符） 的值。 默认情况下，未设置此属性并且会挂起该交换，如果**存储事务集/负载以用于报告**选择，但不是选择 UNB3.2 的值。  
  
4. 单击“确定” 。  
  
### <a name="to-enable-as2-status-reports"></a>若要启用 AS2 状态报告  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点，单击**参与方**节点。  
  
2. 在中**参与方和业务配置文件**窗格中，单击包含你想要启用状态报告的 X12 或 EDIFACT 协议的参与方。  
  
3. 在中**协议**部分中，右键单击你想要启用状态报告，然后单击的协议**属性**。  
  
4. 在中**公用主机设置**部分中，单击**打开报告**。  
  
   > [!NOTE]
   >  此步骤会导致消息条目进入状态报告 UI 中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
5. 在单向协议选项卡中的**协议属性**对话框中，单击**接收方消息跟踪 (NRR)** 页。  
  
6. 在中**接收方消息跟踪 (NRR)** 页上，单击**已为入站编码 AS2 消息启用 NRR**以启用显示传入消息的传输格式。  
  
   > [!NOTE]
   >  当您右键单击 AS2 消息和相关 MDN 状态页中的消息，然后单击时，将显示该消息的传输格式**消息传输格式**。  
  
   > [!NOTE]
   >  **打开报告**属性必须选择要启用不可否认数据库中的任何数据存储。 如果选择此属性或任何启用的不可否认数据库中存储的其他属性，则将显示一个弹出窗口，提示您进行激活 AS2 报告。 如果单击**是**，将为你激活 AS2 报告。  
  
7. 在中**接收方消息跟踪 (NRR)** 页上，单击**已为入站解码 AS2 消息启用 NRR**以启用显示传入消息的解码格式。  
  
8. 在中**接收方消息跟踪 (NRR)** 页上，单击**对出站 MDN 启用 NRR**以启用显示对传入消息的 MDN 响应。  
  
9. 在单向协议选项卡中的**协议属性**对话框中，单击**发件人消息跟踪 (NRR)** 页。  
  
10. 在中**发件人消息跟踪 (NRR)** 页上，单击**已为出站编码 AS2 消息启用 NRR**以启用显示传出消息的传输格式。  
  
11. 在中**发件人消息跟踪 (NRR)** 页上，单击**已为解码后的出站 AS2 消息启用 NRR**以启用显示传出消息的解码格式。  
  
12. 在中**发件人消息跟踪 (NRR)** 页上，单击**对入站 MDN 启用 NRR**以启用对传出消息的 MDN 响应显示。  
  
13. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)   
 [配置 EDI 和 AS2 状态报告](../core/configuring-an-edi-and-as2-status-report.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   