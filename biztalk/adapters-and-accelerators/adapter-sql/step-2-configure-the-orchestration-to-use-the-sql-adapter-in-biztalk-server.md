---
title: 步骤 2： 使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6293758d9891d86e137d07e9735ce37162d6a96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984022"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a>步骤 2： 使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程
![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，执行以下任务：  
  
- 创建 WCF 自定义发送接收端口以发送和接收消息，从 SQL Server 数据库使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 配置此端口以使用在上一步中创建的映射。  
  
- 配置业务流程使用 WCF 自定义端口上一步中部署。  
  
## <a name="prerequisites"></a>必要條件  
 你应已部署 BizTalk 业务流程，你想要配置 WCF 自定义端口，如中所述[步骤 1： 修改 vPrev BizTalk 项目使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1. 生成架构上使用 SQL Server 数据库的操作时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。 您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53)。  
  
2. 导入绑定文件后下, 创建的发送端口**发送端口**文件夹中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
3. 右键单击 WCF 自定义端口，然后依次**属性**。  
  
4. 从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5. 在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，指定凭据以连接到 SQL Server 数据库，然后单击**确定**。  
  
6. 从发送端口属性对话框的左窗格中，单击**入站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**ResponseMap**。  
  
    ![配置入站的映射](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")  
  
7. 从发送端口属性对话框的左窗格中，单击**出站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**RequestMap**。  
  
    ![配置出站映射](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")  
  
8. 单击“确定” 。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置的 BizTalk 应用程序  
  
1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开在其中部署业务流程的 BizTalk 应用程序。  
  
2. 右键单击 BizTalk 应用程序，然后选择**配置**。  
  
3. 从左窗格中，单击业务流程配置。 在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4. 下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
   1.  选择将存放请求消息的文件端口。 BizTalk 业务流程将使用请求消息并将其发送到 SQL Server 数据库。  
  
   2.  选择 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口。  
  
   3.  选择本主题中前面创建的 WCF 自定义发送端口。  
  
   4.  单击“确定” 。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到 BizTalk 项目，将消息发送到 SQL Server 数据库使用基于 WCF 的 vPrev BizTalk 项目的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息以执行插入操作上，SQL Server 数据库中所述[第 3 步： 测试迁移应用程序使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 1： 将 BizTalk 项目迁移到 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)