---
title: "步骤 2： 配置 WCF 自定义单向接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way receive port, configuring
- migration
ms.assetid: e2a8f074-64d5-4e6c-84d0-318fb606c0ba
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6edf75f08bdf6a321188e484eb4f363366f8eb95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a>步骤 2： 配置 WCF 自定义单向接收端口
![步骤 2 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：**在此步骤中，配置要从某个 SAP 系统接收平面文件 IDOC 的 WCF 自定义端口。 配置端口之后, 你可以配置 BizTalk 应用程序以使用 WCF 自定义接收端口。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已生成并部署 SAP 系统从接收到的 Idoc 你 vPrev BizTalk 项目。  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a>若要配置 WCF 自定义单向接收端口  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开要在其下创建接收端口的应用程序。  
  
4.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
5.  在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  
  
6.  上**接收位置**选项卡上，单击**新建**。 **接收位置属性**对话框随即出现。  
  
7.  在**接收位置属性**对话框框中，执行以下操作：  
  
    1.  指定接收位置的名称。  
  
    2.  从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
8.  在**WCF 自定义传输属性**对话框框中，执行以下操作：  
  
    1.  单击**常规**选项卡上，然后在**地址 (URI)**字段中，指定连接 URI 从 SAP 系统接收消息。 连接从 SAP 系统接收消息的 URI 必须采用以下格式：  
  
        ```  
        sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
        ```  
  
         下图显示端口属性对话框中，使用指定的 URI:  
  
         ![连接 URI 从 SAP 接收消息](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")  
  
         有关连接 URI 的详细信息，请参阅[创建与 SAP 系统的连接](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)。  
  
    2.  单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。 请确保指定的接收端口的以下绑定属性。  
  
        |绑定属性|将值设|  
        |----------------------|------------------|  
        |flatFileSegmentIndicator|**SegmentType**。 这表示将平面文件应包含 IDOC 中每个段的段类型。|  
        |padReceivedIdocWithSpaces|**True**。 指定是否用正确的长度为空格填充 IDOC 中的每一行。|  
        |receiveIDocFormat|**字符串**。 这将指定 IDOC 消息，应表示为单个字符串字段。|  
  
         有关绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
    3.  单击**其他**选项卡，然后指定要连接到 SAP 系统的凭据。  
  
    4.  单击**消息**选项卡上，然后在**入站 BizTalk 消息正文**部分中，选择**路径**选项。  
  
    5.  在**正文路径表达式**文本框中，指定要从 XML 消息中提取平面文件 IDOC 的 XPath 查询。 通过这样做，接收端口从 IDOC 中提取数据，并剪裁是的一部分的 XML 标记**ReceiveIdoc**操作的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关详细信息有关的消息架构**ReceiveIdoc**操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
         ![XPath 查询以提取平面 &#45; 文件 IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")  
  
         你必须指定以下 XPath 查询：  
  
        ```  
        /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
        ```  
  
    6.  从**节点编码**下拉列表中，选择**字符串**。  
  
    7.  单击**应用**，然后单击**确定**。  
  
9. 在接收位置属性对话框中，从**接收处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
10. 从**接收管道**下拉列表中，选择**ConvertToXML**。 此平面文件反汇编程序管道已 vPrev BizTalk 项目，将平面文件 IDOC 转换为 XML IDOC 的一部分。  
  
11. 单击 **“确定”**。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置 BizTalk 应用程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，展开其中部署业务流程的 BizTalk 应用程序。  
  
2.  右键单击 BizTalk 应用程序，然后再选择**配置**。  
  
3.  从左窗格中，单击要配置业务流程。 从右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4.  下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
    1.  选择 WCF 自定义接收你在本主题前面创建的端口。  
  
    2.  选择将在其中接收平面文件 IDOC 文件端口。  
  
    3.  单击 **“确定”**。  
  
     有关配置应用程序的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到 BizTalk 项目使用基于 WCF 的 SAP 系统从接收到的 Idoc vPrev BizTalk 项目[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 你必须现在测试迁移的 BizTalk 应用程序接收平面文件 IDOC 中, 所述[步骤 3： 测试迁移应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 迁移 SAP 接收 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)