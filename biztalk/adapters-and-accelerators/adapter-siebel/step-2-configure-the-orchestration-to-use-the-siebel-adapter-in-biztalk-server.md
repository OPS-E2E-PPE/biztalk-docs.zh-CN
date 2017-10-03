---
title: "步骤 2： 与 Siebel 适配器在 BizTalk Server 管理控制台中配置业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0ed6c6609ccca3d13ea0eba46f9e2d0ee6cc14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a>步骤 2： 与 Siebel 适配器在 BizTalk Server 管理控制台中配置业务流程
![步骤 2 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：**在此步骤中，你将要执行以下任务：  
  
-   创建 WCF 自定义发送接收端口来发送和接收来自 Siebel 系统使用消息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 配置此端口，以使用你在上一步中创建的映射。  
  
-   配置业务流程部署中使用 WCF 自定义端口的最后一步。  
  
## <a name="prerequisite"></a>前提条件  
  
-   你必须部署 BizTalk 业务流程你想要配置的 WCF 自定义端口。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1.  当你为操作生成架构 Siebel 系统使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件还添加到 BizTalk 项目。 你可以导入此绑定文件到你的 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)。  
  
2.  导入的绑定文件后下, 创建发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。  
  
3.  右键单击 WCF 自定义端口，然后单击**属性**。  
  
4.  从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5.  在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，并指定要连接到 Siebel 系统的凭据。  
  
6.  单击 **“确定”**。  
  
7.  从发送端口属性对话框的左窗格中，单击**入站映射**。 从右窗格中，单击下的字段**映射**列中，从下拉列表中选择**ResponseMap**。  
  
     ![配置入站的映射](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")  
  
8.  从发送端口属性对话框的左窗格中，单击**出站映射**。 从右窗格中，单击下的字段**映射**列中，从下拉列表中选择**RequestMap**。  
  
     ![配置出站映射](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")  
  
9. 单击 **“确定”**。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置 BizTalk 应用程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，展开其中部署业务流程的 BizTalk 应用程序。  
  
2.  右键单击 BizTalk 应用程序，然后再选择**配置**。  
  
3.  从左窗格中，单击要配置业务流程。 从右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4.  下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
    1.  选择将放置请求消息的位置的文件端口。 BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。  
  
    2.  选择 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口。  
  
    3.  选择你在本主题前面创建的 WCF 自定义发送端口。  
  
    4.  单击 **“确定”**。  
  
     有关配置应用程序的详细信息，请参阅"如何为配置应用程序"在[http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到将消息发送到 Siebel 系统使用基于 WCF 的 BizTalk 项目 vPrev BizTalk 项目[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 你现在必须通过以下方式测试迁移的 BizTalk 应用程序通过发送以调用上帐户在业务组件，该插入操作的请求消息中所述[步骤 3： 测试迁移应用程序与 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 2： 迁移中 Siebel 的 BizTalk 项目](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)