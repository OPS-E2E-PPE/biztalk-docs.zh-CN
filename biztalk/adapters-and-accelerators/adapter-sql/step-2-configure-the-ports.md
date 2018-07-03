---
title: 步骤 2： 配置的端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e804da96-26ae-482d-b6e1-67af24d639d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe05185c625825c795ee89dff10d5be9ae6a68d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973726"
---
# <a name="step-2-configure-the-ports"></a>步骤 2： 配置的端口
![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **完成时间：** 15 分钟  
  
 **目标：** 在此步骤中，创建中的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 创建业务流程中创建的每个逻辑端口的物理端口。 您将创建以下端口：  
  
- 一个单向 WCF 自定义接收端口以接收到的更改的通知消息**员工**SQL Server 数据库中的表。  
  
- 请求-响应 WCF 自定义发送端口以将请求消息发送和接收用于调用的响应**UPDATE_EMPLOYEE**存储过程以及对执行插入操作**Purchase_Order**表。 在业务流程中，您可以使用相同的发送端口来执行这两个操作。 同样，在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您将单个发送端口用于这两种操作。  
  
- 一个单向发送端口以发送 Insert 操作的响应。 在本教程中，因为需要通知通过电子邮件，购买院系创建此发送端口作为 SMTP 端口。  
  
## <a name="prerequisites"></a>必要條件  
 你必须已完成[步骤 1： 部署业务流程](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md))。  
  
### <a name="to-create-a-physical-one-way-receive-port"></a>若要创建单向物理接收端口  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在左侧控制台树中，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**刷新**。  
  
3. 展开**BizTalk 组**，展开**应用程序**，然后展开**SampleApplication**。 对于本教程，您可以创建所有端口和 SampleApplication 应用程序中的应用程序。  
  
4. 按照下的"部署适配器的接收的消息从 SQL Server"部分的说明进行操作[使用 WCF 自定义适配器和 SQL 适配器配置端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)。 端口的名称为**NotifyReceivePort**。  
  
5. 请确保设置以下的绑定属性，以将适配器配置为接收到的更改通知**员工**表。  
  
   |绑定属性|ReplTest1|  
   |----------------------|-----------|  
   |**InboundOperationType**|将此设置为**通知**。|  
   |**NotificationStatement**|将此设置为：<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注意：** 您必须专门的列名称在语句中指定此 Select 语句中所示。 此外，您必须始终指定表名称以及该架构名称，例如， `dbo.Employee`。|  
   |**NotifyOnListenerStart**|将此设置为 **，则返回 True**。|  
  
    有关不同的绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
### <a name="to-create-a-request-response-send-port-for-two-operations"></a>若要创建请求-响应发送端口的两个操作  
  
1. 按照下的"部署适配器用于发送消息到 SQL Server"部分的说明进行操作[使用 WCF 自定义适配器和 SQL 适配器配置端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)。 端口的名称为**SQLOutboundPort**。  
  
2. 由于正在执行两个操作使用的相同发送端口，必须使用动态操作映射来指定该操作的操作。 在中配置端口时**操作**框中，按以下方式指定操作映射：  
  
   ```  
   <BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
     <Operation Name="UpdateEmp" Action="TypedProcedure/dbo/UPDATE_EMPLOYEE" />  
     <Operation Name="InsertPO" Action="TableOp/Insert/dbo/Purchase_Order" />  
   </BtsActionMapping>  
   ```  
  
    请注意，在业务流程，您创建请求-响应发送端口的两个操作： **UpdateEmp**并**InsertPO**。 因此，物理端口配置中提供的动态操作映射中的相同操作名称。 在上面的摘录中，为操作**UpdateEmp**操作是`TypedProcedure/dbo/UPDATE_EMPLOYEE`。 同样，对于操作**InsertPO**操作是`TableOp/Insert/dbo/Purchase_Order`。  
  
3. 您还必须配置发送端口以使用在业务流程，以将响应消息的映射中创建的映射器**UPDATE_EMPLOYEE**存储过程插入操作的请求消息到**Purchase_顺序**表。 为此：  
  
   1. 右键单击在 SQLOutboundPort[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，然后单击**属性**。  
  
   2. 从**SQLOutboundPort – 发送端口属性**对话框中，从左窗格中，单击**出站映射**。  
  
   3. 从右窗格中，在**出站映射**框中，单击下的单元格**地图**列中，并从下拉列表中，选择**Transform_1**。 这是在 BizTalk 业务流程中创建的映射名称[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。  
  
       单击“确定” 。  
  
       ![配置出站映射](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-010-map-ports.gif "sql_adap_tut_010_map_ports")  
  
### <a name="to-create-an-smtp-send-port"></a>若要创建 SMTP 发送端口  
  
1. 请按照下面的说明"如何配置 SMTP 发送端口与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台"部分[ http://go.microsoft.com/fwlink/?LinkId=141549 ](http://go.microsoft.com/fwlink/?LinkId=141549)。 端口的名称为**EmailResponse**。  
  
2. 端口配置的一部分，指定有关采购部门的电子邮件地址**到**属性。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中创建 WCF 自定义接收端口从 SQL Server 中接收通知、 在 SQL Server 上执行操作的 WCF 自定义发送端口和发送响应从 SQL Server 作为电子邮件发送给采购部门的 SMTP 端口。  
  
## <a name="next-steps"></a>后续步骤  
 配置和启动 BizTalk 应用程序，如中所述[第 3 步： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [步骤 1： 部署业务流程](../../adapters-and-accelerators/adapter-sql/step-1-deploy-the-orchestration.md)   
 [步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [第 5 课：部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)