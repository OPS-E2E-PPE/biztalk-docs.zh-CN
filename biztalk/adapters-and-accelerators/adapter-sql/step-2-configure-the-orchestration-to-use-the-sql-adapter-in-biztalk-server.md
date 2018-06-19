---
title: 步骤 2： 在 BizTalk Server 管理控制台中使用的 SQL 适配器配置业务流程 |Microsoft 文档
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
ms.openlocfilehash: 9b090ae83f0ca36bb4ae95795480d5f0d1661f16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223789"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a>步骤 2： 在 BizTalk Server 管理控制台中使用的 SQL 适配器配置业务流程
![步骤 2 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，你将要执行以下任务：  
  
-   创建 WCF 自定义发送接收要发送和接收来自 SQL Server 数据库使用的消息端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 配置此端口，以使用你在上一步中创建的映射。  
  
-   配置业务流程部署在上面的步骤以使用 WCF 自定义端口。  
  
## <a name="prerequisites"></a>先决条件  
 你应该部署你想要配置的 WCF 自定义端口中, 所述 BizTalk 业务流程[步骤 1： 修改 vPrev BizTalk 项目使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1.  当生成上使用 SQL Server 数据库的操作的架构[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件还添加到 BizTalk 项目。 你可以导入此绑定文件到你的 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53)。  
  
2.  导入的绑定文件后下, 创建发送端口**发送端口**文件夹中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
3.  右键单击 WCF 自定义端口，然后单击**属性**。  
  
4.  从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5.  在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡上，指定的凭据以连接到 SQL Server 数据库，然后单击**确定**。  
  
6.  从发送端口属性对话框的左窗格中，单击**入站映射**。 从右窗格中，单击下的字段**映射**列中，从下拉列表中选择**ResponseMap**。  
  
     ![配置入站的映射](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")  
  
7.  从发送端口属性对话框的左窗格中，单击**出站映射**。 从右窗格中，单击下的字段**映射**列中，从下拉列表中选择**RequestMap**。  
  
     ![配置出站映射](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")  
  
8.  单击 **“确定”**。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置 BizTalk 应用程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开其中部署业务流程的 BizTalk 应用程序。  
  
2.  右键单击 BizTalk 应用程序，然后再选择**配置**。  
  
3.  从左窗格中，单击要配置业务流程。 从右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4.  下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
    1.  选择将放置请求消息的位置的文件端口。 BizTalk 业务流程将使用请求消息，并将其发送到的 SQL Server 数据库。  
  
    2.  选择 BizTalk 业务流程放置包含从 SQL Server 数据库响应的响应消息的位置的文件端口。  
  
    3.  选择你在本主题前面创建的 WCF 自定义发送端口。  
  
    4.  单击 **“确定”**。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到将消息发送到使用基于 WCF 的 SQL Server 数据库的 BizTalk 项目 vPrev BizTalk 项目[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你现在必须通过以下方式测试迁移的 BizTalk 应用程序通过发送要执行 SQL Server 数据库中，插入操作的请求消息中所述[步骤 3： 测试迁移应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 将 BizTalk 项目迁移到 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)