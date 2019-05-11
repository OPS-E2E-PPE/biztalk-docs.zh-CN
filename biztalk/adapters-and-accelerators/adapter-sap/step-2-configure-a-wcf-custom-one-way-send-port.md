---
title: 第 2 步：配置 WCF 自定义单向发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5daec84fac1987fccc015da9d457e26f86dea61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372841"
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a>第 2 步：配置 WCF 自定义单向发送端口
![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，你配置用于将平面文件 IDOC 发送到 SAP 系统的 WCF 自定义端口。 后配置端口时，BizTalk 应用程序使用 WCF 自定义发送端口配置。  
  
## <a name="prerequisites"></a>先决条件  
 你必须构建和部署 vPrev BizTalk 项目以将 Idoc 发送到 SAP 系统。  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a>若要配置 WCF 自定义单向发送端口  
  
1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 展开要在其下创建发送端口的应用程序。  
  
4. 右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
5. 在中**发送端口属性**对话框中，在**常规**选项卡上，键入发送端口的名称。  
  
6. 从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。  
  
7. 在中**Wcf-custom 传输属性**对话框框中，执行以下操作：  
  
   1. 单击**常规**选项卡上，然后在**地址 (URI)** 字段中，指定连接 URI，将消息发送到 SAP 系统。 有关连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
       ![在发送端口中指定的连接 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")  
  
   2. 上**常规**选项卡上，在**操作**文字框中，键入操作的操作。 若要发送平面文件 IDOC，必须使用**SendIdoc**操作公开的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 **SendIdoc**操作允许适配器客户端发送 Idoc 具有弱类型的架构。 有关详细信息，请参阅[sap 的 Idoc 的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)。 下图显示**操作**的操作的文本框中**SendIdoc**操作。  
  
       ![在发送端口中指定操作](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")  
  
   3. 单击**绑定**选项卡上，并从**绑定类型**下拉列表中，选择**sapBinding**。  
  
   4. 单击**凭据**选项卡上，并指定用于连接到 SAP 系统的凭据。  
  
   5. 单击**消息**选项卡上，然后在**出站 WCF 消息正文**部分中，选择**模板**选项。  
  
   6. 在中**XML**文字框中，指定将用于构造 WCF 消息的模板。 通过此操作，创建一条消息，符合**SendIdoc**操作的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 有关的消息结构的详细信息**SendIdoc**操作，请参阅[IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)。  
  
       ![指定出站 WCF 消息的模板](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")  
  
       对于 SendIdoc 操作中，您必须指定以下模板：  
  
      ```  
      <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
      <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
      </SendIdoc>  
      ```  
  
       在前面的模板，`bts-msg-body`是使用与文件相关联的平面文件拆装器创建的 XML IDOC 接收端口。 XML IDOC 封装在 SendIdoc 消息。  
  
   7. 单击**Apply**，然后单击**确定**。  
  
8. 在中**发送端口属性**对话框中，从**发送处理程序**下拉列表中，选择**BizTalkServerApplication**。  
  
9. 从**发送管道**下拉列表中，选择**ConvertToFlatFile**。 此平面文件组装器管道已经 vPrev BizTalk 项目的一部分，用于将 XML IDOC 转换为平面文件 IDOC。  
  
10. 单击“确定” 。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置的 BizTalk 应用程序  
  
1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。  
  
2. 右键单击 BizTalk 应用程序，然后选择**配置**。  
  
3. 从左窗格中，单击业务流程配置。 在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4. 下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
   1. 选择您将在何处放置平面文件 IDOC 的文件端口。  
  
   2. 选择本主题中前面创建的 WCF 自定义发送端口。  
  
   3. 单击“确定” 。  
  
      有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkId=102360 ](http://go.microsoft.com/fwlink/?LinkId=102360)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到 BizTalk 项目，将 Idoc 发送到 SAP 系统使用基于 WCF 的 vPrev BizTalk 项目的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 你必须现在测试已迁移的 BizTalk 应用程序通过发送平面文件 IDOC 中所述[步骤 3:测试已迁移应用程序](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：迁移 SAP 发送 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)