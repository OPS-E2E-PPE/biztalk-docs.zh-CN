---
title: "步骤 2： 添加常见架构 v2.3.1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba84c9f45c477aefe7615eca906c40014b06bd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-common-schemas-for-v231"></a>步骤 2： 添加常见 v2.3.1 架构
在此步骤中，你可以创建基于 BTAHL7231Common 项目模板的新项目。 此模板包含三个常见的架构 （适用于数据类型、 线段和表值）， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 用于验证 v2.3.1 消息实例。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 v2.3.1 架构，包括将使用传入的批处理中的单个消息的架构与结合使用这些常见的架构 (ADT ^ A03)。  
  
 在步骤结束时，你的程序集分配强密钥，并部署。 无需创建第二个强密钥;你可以使用你在中创建的强密钥[步骤 1： 添加标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)。  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a>若要添加 v2.3.1 公共架构和部署程序集  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
3.  在**模板**部分中，选择**BTAHL7V231Common 项目**。  
  
4.  在**名称**框中，输入**BTAHL7V231Common 项目**作为项目名称。  
  
5.  在**解决方案**框中，选择**将添加到解决方案**。  
  
6.  单击 **“确定”**。  
  
    > [!NOTE]
    >  在解决方案资源管理器，三个架构 （datatypes_231.xsd、 segments_231.xsd 和 tablevalues_231.xsd） 包含在项目中。  
  
7.  在解决方案资源管理器，右键单击**BTAHL7V231Common 项目**，然后单击**属性**。  
  
8.  在 BTAHL7V231Common 属性页对话框中，单击**签名**。  
  
9. 检查**对程序集签名**复选框。  
  
10. 在选择强名称密钥文件下拉列表中，选择列表中。  
  
11. 浏览到**: \Batching 教程**，选择**key.snk**，然后单击**打开**。  
  
12. 右键单击**BTAHL7V231Common**，然后单击**部署**。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。  
  
 继续执行[步骤 3： 添加触发器事件 （消息） 架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)。