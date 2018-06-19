---
title: 步骤 3： 添加触发器事件 （消息） 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 439caac8f1da151a9f203a1372039aaeedbfe83c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25960827"
---
# <a name="step-3-add-a-trigger-event-message-schema"></a>步骤 3： 添加触发器事件 （消息） 架构
在此步骤中，你创建新的项目基于空[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]项目模板。 将架构添加到此项目，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将用于验证传入的批处理中消息 (ADT ^ A03)。 添加对包含 v2.3.1 通用架构的项目的引用、 为该项目中，指定强名称，然后部署该项目。  
  
### <a name="to-add-the-project-containing-the-message-schema"></a>若要添加包含的消息架构的项目  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], 上 **文件** 菜单上，指向 **新建**, ，然后单击 **项目**。  
  
2.  在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
3.  在**模板**部分中，选择**空 BTAHL7 项目**。  
  
4.  在**名称**框中，输入**BTAHL7V231Body**作为项目名称。  
  
5.  在**解决方案**框中，选择**将添加到解决方案**。  
  
6.  单击 **“确定”**。  
  
7.  在解决方案资源管理器，新的项目，节点下右键单击**引用**，然后单击**添加引用**。  
  
8.  在添加引用对话框中，在**项目**选项卡上，单击**BTAHL7V231Common 项目**中**项目名称**列中，单击**添加**，然后单击**确定**。  
  
### <a name="to-add-the-schema-to-the-project"></a>若要将架构添加到项目  
  
1.  在解决方案资源管理器，右键单击**BTAHL7V231Body**，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，展开**BizTalk 项目项**，然后单击**BTAHL7 架构**。 在**模板**窗格中，单击**BTAHL7 架构**，然后单击**添加**。  
  
3.  在**HL7 架构选择器**对话框框中，执行以下操作：  
  
    |使用此选项|動作|  
    |--------------|----------------|  
    |**Message 类**|保留**V2.X**为选中状态。|  
    |**版本**|选择**2.3.1**。|  
    |**消息类型**|选择**ADT**。|  
    |**触发器事件**|选择**A03**。|  
  
4.  单击**创建**若要将架构添加到项目，然后单击**取消**以关闭对话框。 请注意该 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 已添加到 BTAHL7V231Body 项目 ADT_A03_231_GLO_DEF.xsd 架构。  
  
### <a name="to-assign-a-strong-key-and-deploy"></a>分配一个强密钥和部署  
  
1.  在解决方案资源管理器，右键单击**BTAHL7V231Body**，然后单击**属性**。  
  
2.  在 BTAHL7V231Body 属性页对话框中，单击**签名**。  
  
3.  检查**对程序集签名**复选框。  
  
4.  在**选择强名称密钥文件**下拉列表中，选择**\<浏览...\>.**  
  
5.  浏览到 **\<*驱动器*\>: \Batching 教程**，选择**key.snk**，然后单击**打开**。  
  
6.  在解决方案资源管理器，右键单击**BTAHL7V231Body**，然后单击**部署**。 确保在输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示 successful-deploy 消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。  
  
 继续执行[步骤 4： 创建用于接受批处理消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)。