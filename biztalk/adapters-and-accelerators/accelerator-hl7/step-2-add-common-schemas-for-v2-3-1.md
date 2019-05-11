---
title: 第 2 步：添加适用于 v2.3.1 的通用架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da98fe6c-4776-4cb8-8454-af3128dea4ab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772b38911ee2f6896588909cb4ae9a6f33cb42b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288835"
---
# <a name="step-2-add-common-schemas-for-v231"></a>第 2 步：添加适用于 v2.3.1 的通用架构
在此步骤中，你创建基于 BTAHL7231Common 项目模板的新项目。 此模板包含的三个常见架构 （适用于数据类型、 段，以及表值） 的 Microsoft BizTalk Accelerator HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 用来验证适用于版本 v2.3.1 消息实例。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] HL7 适用于版本 v2.3.1 架构，包括将使用传入的批中的单个消息的架构与结合使用这些常见的架构 (ADT ^ A03)。  
  
 在此步骤结束时，对程序集分配强密钥和部署。 不需要创建第二个强密钥;可以使用你在中创建的强密钥[步骤 1:添加标头及确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)。  
  
### <a name="to-add-v231-common-schemas-and-deploy-the-assembly"></a>若要添加适用于版本 v2.3.1 的通用架构并将其部署该程序集  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  
  
2. 在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
3. 在中**模板**部分中，选择**BTAHL7V231Common 项目**。  
  
4. 在中**名称**框中，输入**BTAHL7V231Common 项目**作为项目名称。  
  
5. 在中**解决方案**框中，选择**将添加到解决方案**。  
  
6. 单击“确定” 。  
  
   > [!NOTE]
   >  在解决方案资源管理器，在项目中包括三个架构 （datatypes_231.xsd、 segments_231.xsd 和 tablevalues_231.xsd）。  
  
7. 在解决方案资源管理器中右键单击**BTAHL7V231Common 项目**，然后单击**属性**。  
  
8. 在 BTAHL7V231Common 属性页对话框中，单击**签名**。  
  
9. 检查**为程序集签名**复选框。  
  
10. 在选择强名称密钥文件下拉列表中，选择列表中。  
  
11. 浏览到 **: \Batching 教程**，选择**key.snk**，然后单击**打开**。  
  
12. 右键单击**BTAHL7V231Common**，然后单击**部署**。 请确保在输出窗口中将显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的架构。  
  
    请继续执行[步骤 3:添加触发器事件 （消息） 架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)。