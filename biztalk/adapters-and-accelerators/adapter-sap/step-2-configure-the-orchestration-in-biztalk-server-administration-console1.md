---
title: 步骤 2： 配置 BizTalk Server 管理控制台 1 中的业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration, configruing in BizTalk Server Administration console
- WCF-Custom port, creating
- migration
ms.assetid: fb057bce-5702-4ea0-8ed5-e299d3a78a11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 696315b895ff778c0cc8f4f929cb62a4ba110846
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015054"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a>步骤 2： 在 BizTalk Server 管理控制台中配置业务流程
![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，执行以下任务：  
  
- 创建 WCF 自定义发送接收端口以发送和接收来自 SAP 系统使用的消息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 配置此端口以使用在上一步中创建的映射。  
  
- 配置业务流程中使用 WCF 自定义端口的最后一步部署。  
  
## <a name="prerequisite"></a>先决条件  
  
-   部署你想要配置 WCF 自定义端口的 BizTalk 业务流程。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1. 当生成架构的 RFC 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。 您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf)。  
  
2. 导入绑定文件后下, 创建的发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。  
  
3. 右键单击 WCF 自定义端口，然后依次**属性**。  
  
4. 从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5. 在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后指定用于连接到 SAP 系统的凭据。  
  
6. 单击“确定” 。  
  
7. 从发送端口属性对话框的左窗格中，单击**入站映射**。 在右窗格中，单击下的字段**地图**列中，并从下拉列表中选择**ResponseMap**。  
  
    ![WCF 自定义端口上配置入站的映射](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")  
  
8. 从发送端口属性对话框的左窗格中，单击**出站映射。** 在右窗格中，单击下的字段**地图**列中，并从下拉列表中选择**RequestMap**。  
  
    ![WCF 自定义端口上配置出站映射](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")  
  
9. 单击“确定” 。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置的 BizTalk 应用程序  
  
1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开在其中部署业务流程的 BizTalk 应用程序。  
  
2. 右键单击 BizTalk 应用程序，然后选择**配置**。  
  
3. 从左窗格中，单击业务流程配置。 在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4. 下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
   1. 选择将存放请求消息的文件端口。 BizTalk 业务流程将使用请求消息并将其发送到 SAP 系统。  
  
   2. 选择 BizTalk 业务流程放置包含来自 SAP 系统的响应的响应消息的位置的文件端口。  
  
   3. 选择本主题中前面创建的 WCF 自定义发送端口。  
  
   4. 单击“确定” 。  
  
      有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到 BizTalk 项目，将消息发送到 SAP 系统使用基于 WCF 的 vPrev BizTalk 项目的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息来调用 SD_RFC_CUSTOMER_GET RFC，如中所述[第 3 步： 测试迁移应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：迁移 SAP RFC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)