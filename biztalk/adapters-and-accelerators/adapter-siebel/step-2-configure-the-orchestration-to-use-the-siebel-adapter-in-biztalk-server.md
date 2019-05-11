---
title: 第 2 步：使用 Siebel 适配器在 BizTalk Server 管理控制台中配置业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8415e273956a430fb56fea579e8cbb2a0de880dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370618"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a>第 2 步：使用 Siebel 适配器在 BizTalk Server 管理控制台中配置业务流程
![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，您可以执行以下任务：  
  
- 创建 WCF 自定义发送接收端口以发送和接收消息从 Siebel 系统使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 配置此端口以使用在上一步中创建的映射。  
  
- 配置业务流程中使用 WCF 自定义端口的最后一步部署。  
  
## <a name="prerequisite"></a>先决条件  
  
-   你必须部署你想要配置 WCF 自定义端口的 BizTalk 业务流程。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1. 生成对 Siebel 系统使用的操作的架构时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。 您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)。  
  
2. 导入绑定文件后下, 创建的发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。  
  
3. 右键单击 WCF 自定义端口，然后依次**属性**。  
  
4. 从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5. 在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡上，并指定要连接到 Siebel 系统的凭据。  
  
6. 单击“确定” 。  
  
7. 从发送端口属性对话框的左窗格中，单击**入站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**ResponseMap**。  
  
    ![配置入站的映射](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")  
  
8. 从发送端口属性对话框的左窗格中，单击**出站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**RequestMap**。  
  
    ![配置出站映射](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")  
  
9. 单击“确定” 。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置的 BizTalk 应用程序  
  
1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。  
  
2. 右键单击 BizTalk 应用程序，然后选择**配置**。  
  
3. 从左窗格中，单击业务流程配置。 在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4. 下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
   1. 选择将存放请求消息的文件端口。 BizTalk 业务流程将使用请求消息，并将其发送到 Siebel 系统。  
  
   2. 选择 BizTalk 业务流程放置包含来自 Siebel 系统的响应的响应消息的位置的文件端口。  
  
   3. 选择本主题中前面创建的 WCF 自定义发送端口。  
  
   4. 单击“确定” 。  
  
      有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到 BizTalk 项目，将消息发送到使用基于 WCF 的 Siebel 系统 vPrev BizTalk 项目的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息调用帐户业务组件上的插入操作，如中所述[步骤 3:测试迁移应用程序使用 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：在 Siebel 的 BizTalk 项目迁移](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)