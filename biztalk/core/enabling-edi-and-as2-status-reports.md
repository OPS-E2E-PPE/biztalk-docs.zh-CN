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
ms.openlocfilehash: e5f0f76008fe7d5ae7bd5b868e9ad81fa9038e04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978014"
---
# <a name="enabling-edi-and-as2-status-reports"></a>启用 EDI 和 AS2 状态报告
本主题介绍如何配置 EDI 和 AS2 状态报告中的**组概述**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
 状态报告跟踪数据按照在以下过程中选择的存储属性存储在 BizTalk 跟踪数据库 (BizTalkDTADb) 中。 你可以配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为每个协议启用状态报告。 根据所存储数据的数量多少，应根据需要定期将活动存储中的数据存档并最终将这些数据从存档存储中清除。 有关管理 BizTalkDTADb 数据库的详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。  
  
 你可以通过以下三种方式启用状态报告：  
  
- 为解析到某个协议的入站或出站 EDI 交换启用状态报告。  
  
- 对 EDI 备用协议属性启用状态报告，以便为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法确定其协议的 EDI 交换激活状态报告。  
  
- 对 AS2 消息启用状态报告。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组或 BizTalk Server B2B Operators 组成员的身份登录。  
  
### <a name="to-enable-edi-status-reports-for-an-agreement"></a>为协议启用 EDI 状态报告  
  
1. 在中**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**控制台中，单击**方**节点下的[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点。  
  
2. 在中**参与方和业务配置文件**窗格中，单击包含你想要启用状态报告的 X12 或 EDIFACT 协议的参与方。  
  
3. 在中**协议**部分中，右键单击你想要启用状态报告，然后单击的协议**属性**。  
  
4. 在中**常规**选项卡上，在**公用主机设置**部分中，单击**打开报告**。  
  
   > [!NOTE]
   >  此步骤的作用是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的状态报告 UI 中输入消息条目。  
  
5. 选择**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。  
  
   > [!NOTE]
   >  如果在激活批处理业务流程实例的情况下启用事务集存储，则不会为创建的批存储事务集。 但是，如果在激活批处理业务流程实例的情况下禁用事务集存储，则会在批处理过程中禁用存储。  
  
6. 单击“确定” 。  
  
7. 重新启动 BizTalk 服务（在“计算机管理”对话框中）。 如果你的解决方案中正在使用 AS2EdiReceive 管道或 AS2EdiSend 管道，重新启动 IIS Admin 服务 (使用*iisreset*命令)，因此也。  
  
   > [!NOTE]
   >  激活或停用 EDI 状态报告功能后，需要重新启动 BizTalk 服务，以使更改生效。 如果在解决方案中使用了 AS2EdiReceive 或 AS2EdiSend 管道，则需要重新启动 BizTalk 服务和 IIS 服务，以使更改生效。 请注意，启用 AS2 状态报告时不需要这么做。  
  
### <a name="to-enable-edi-status-reports-for-fallback-agreements"></a>为备用协议启用 EDI 状态报告  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**节点，右键单击**参与方**，然后选择**X12 后备设置**或**EDIFACT 后备设置**。  
  
   > [!NOTE]
   >  当在备用协议中配置状态报告时，只有在未确定任何消息协议的情况下才可应用该配置。  
  
2. 在中**回退设置常规页**选项卡上，单击**激活 EDI 报告**。  
  
   > [!NOTE]
   >  此步骤的作用是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的状态报告 UI 中输入消息条目。  
  
3. 选择**存储事务集/负载以用于报告**来存储事务集跟踪 (BizTalkDTADb) 数据库的 EDI 表中。  
  
   > [!NOTE]
   >  **对于 EDIFACT 编码的消息**： 如果选择此属性，还必须在 EDI 全局属性对话框中的 UNB 段定义页中选择 UNB3.2 字段 （代码限定符） 的值。 默认情况下，未设置此属性并且会挂起该交换，如果**存储事务集/负载以用于报告**选择，但不是选择 UNB3.2 的值。  
  
4. 单击“确定” 。  
  
### <a name="to-enable-as2-status-reports"></a>启用 AS2 状态报告  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]并**BizTalk 组**节点，单击**参与方**节点。  
  
2. 在中**参与方和业务配置文件**窗格中，单击包含你想要启用状态报告的 X12 或 EDIFACT 协议的参与方。  
  
3. 在中**协议**部分中，右键单击你想要启用状态报告，然后单击的协议**属性**。  
  
4. 在中**公用主机设置**部分中，单击**打开报告**。  
  
   > [!NOTE]
   >  此步骤的作用是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的状态报告 UI 中输入消息条目。  
  
5. 在单向协议选项卡中的**协议属性**对话框中，单击**接收方消息跟踪 (NRR)** 页。  
  
6. 在中**接收方消息跟踪 (NRR)** 页上，单击**已为入站编码 AS2 消息启用 NRR**以启用显示传入消息的传输格式。  
  
   > [!NOTE]
   >  当您右键单击 AS2 消息和相关 MDN 状态页中的消息，然后单击时，将显示该消息的传输格式**消息传输格式**。  
  
   > [!NOTE]
   >  **打开报告**属性必须选择要启用不可否认数据库中的任何数据存储。 如果选择此属性或任何其他用于在不可否认数据库中启用存储的属性，则会显示弹出窗口，提示你激活 AS2 报告。 如果单击**是**，将为你激活 AS2 报告。  
  
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