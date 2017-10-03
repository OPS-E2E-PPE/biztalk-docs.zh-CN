---
title: "步骤 3： 创建和部署触发器事件 （消息） Project_hl7_main |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7abfcf363d26d068fab067378eb61d5bcf5c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a>步骤 3： 创建和部署触发器事件 （消息） Project_hl7_main
在此步骤中，你创建的触发器事件消息所使用的架构。 例如，许可放电并传输系统 (ADT)，将发送一条消息到医院信息系统 (HIS)。 此架构用于定义你的消息的格式。  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>若要创建触发器事件消息的项目  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。  
  
3.  在**模板**列表中，单击**空 BTAHL7 项目**。  
  
4.  在**名称**字段中，键入**BTAHL7V24Body 项目**，然后单击**确定**。  
  
5.  在解决方案资源管理器中的新节点下**BTAHL7V24Body**项目，右键单击**引用**，然后单击**添加引用**。  
  
6.  在添加引用对话框中，单击**项目**选项卡上，选择**Interrogative_24Schemas**，单击**添加**，然后单击**确定**。  
  
## <a name="step-3a-add-the-schemas"></a>步骤 3A： 将架构添加  
 使用以下过程将新架构添加到项目。  
  
#### <a name="to-add-the-schemas-to-the-project"></a>若要将架构添加到项目  
  
1.  在解决方案资源管理器，右键单击**BTAHL7V24Body 项目**，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，展开**BizTalk 项目项**，然后双击**BTAHL7 架构**右窗格中。  
  
3.  在 HL7 架构选择器对话框中，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Message 类**|保留**V2.X**选。|  
    |**版本**|选择**2.4**。|  
    |**消息类型**|选择**QRY**。|  
    |**触发器事件**|选择**Q01**。|  
  
4.  单击**完成**将该架构添加到项目。  
  
     这将创建查询架构文件 QRY_Q01_24_GLO_DEF.xsd。  
  
    > [!NOTE]
    >  不要关闭 HL7 架构选择器对话框。  
  
5.  在 HL7 架构选择器对话框中，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Message 类**|保留**V2.X**选。|  
    |**版本**|选择**2.4**。|  
    |**消息类型**|选择**DSR**。|  
    |**触发器事件**|选择**Q01**。|  
  
6.  单击**完成**将该架构添加到项目。  
  
     这将创建响应架构文件 DSR_Q01_24_GLO_DEF.xsd。  
  
7.  单击**取消**关闭**HL7 架构选择器**对话框。  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>步骤 3B： 向程序集分配强密钥和部署  
 使用以下过程向程序集分配强密钥，然后将部署程序集。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>分配一个强密钥和部署程序集  
  
1.  在解决方案资源管理器，右键单击**BTAHL7V24Body**项目，，然后单击**属性**。  
  
2.  在**BTAHL7V24Body 属性页**对话框中，单击**程序集**。  
  
3.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
4.  在**程序集密钥文件**对话框中，浏览到\<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > HL7\SDK\ 快捷键Interrogative 教程，则单击**key.snk**，然后单击**打开**。  
  
5.  在**BTAHL7V24Body 属性页**对话框中，单击**确定**以保存所做的更改。  
  
6.  在解决方案资源管理器中右键单击**BTAHL7V24Body 项目**，然后单击**部署**。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示成功部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。  
  
 继续执行[步骤 4： 创建用于接受 ADT 查询消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)。