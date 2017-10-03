---
title: "步骤 3： 创建和部署的触发器事件 （消息） 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf96bdc546223b68677b642944265c22d2ce4b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a>步骤 3： 创建和部署的触发器事件 （消息） 项目
在此步骤中，你的触发器事件消息创建架构。 例如，你可能在许可放电并传输系统 (ADT) 发送到医院信息系统 (HIS) 的一条消息。 你需要此架构来定义你的消息的格式。  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a>若要创建触发器事件消息的项目  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。  
  
3.  在模板部分中，单击**空 BTAHL7 项目**中**名称**框中，键入**BTAHL7V231Body 项目**，然后单击**确定**。  
  
4.  在解决方案资源管理器，新的项目，节点下右键单击**引用**，然后单击**添加引用**。  
  
5.  在添加引用对话框中，在**项目**选项卡上，选择**BTAHL7V231Common Project1**，单击**添加**，然后单击**确定**。  
  
## <a name="step-3a-add-the-schema"></a>步骤 3A： 将架构添加  
 使用以下过程将新架构添加到项目。  
  
#### <a name="to-add-the-schema-to-the-project"></a>若要将架构添加到项目  
  
1.  在解决方案资源管理器，右键单击**BTAHL7V231Body 项目**，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，在**类别**部分中，展开**BizTalk 项目项**，然后选择**BTAHL7 架构**。  
  
3.  在模板部分中，双击**BTAHL7 架构**。  
  
4.  在 HL7 架构选择器对话框中，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Message 类**|保留默认的**V2.X**选。|  
    |**版本**|选择**2.3.1**。|  
    |**消息类型**|选择**ADT**。|  
    |**触发器事件**|选择**A03**。|  
  
5.  单击**完成**将该架构添加到项目。  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a>步骤 3B： 向程序集分配强密钥和部署  
 使用以下过程向程序集分配强密钥，然后将部署程序集。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>分配一个强密钥和部署程序集  
  
1.  在解决方案资源管理器，右键单击**BTAHL7V231Body 项目**，然后单击**属性**。  
  
2.  在项目属性页页中，单击**程序集**。  
  
3.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 (**...**) 按钮。  
  
4.  在程序集密钥文件对话框中，浏览到\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\End 端到端教程中，单击**key.snk**，然后单击**打开**。  
  
5.  在项目属性页对话框中，单击**确定**以保存所做的更改。  
  
6.  在解决方案资源管理器中右键单击**BTAHL7V231Body 项目**，然后单击**部署**。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示成功部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。  
  
 继续执行[步骤 4： 创建用于接受 ADT 接收端口 ^ A03 消息从 ADT 系统使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)。