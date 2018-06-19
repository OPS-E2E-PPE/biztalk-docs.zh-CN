---
title: 步骤 4： 创建架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce9ea850632327e257909e1c7d4b60117865e46
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961731"
---
# <a name="step-4-create-the-schemas"></a>步骤 4： 创建架构
在此步骤中，创建一个新的项目 (**BTAHL7 项目**)，其中包含此项目的项目： 架构、 映射和业务流程。 然后创建架构 (**Doorbell.xsd**) 传入的 XML 编码的消息，然后选择现有架构 (**ADT_A04_22_GLO_DEF.xsd**) 为传出的 HL7 编码消息。 您可以使用这些架构来定义的业务流程中交换的消息的结构。  
  
### <a name="to-create-the-schemas"></a>若要创建架构  
  
1.  在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。  
  
2.  在新建项目对话框中，展开**BizTalk 项目**文件夹，，然后单击**BTAHL7Projects**文件夹。  
  
3.  在**模板**窗格中，单击**空 BTAHL7 项目**。  
  
4.  在**名称**字段中，键入**BTAHL7 项目**作为项目名称。  
  
5.  在**解决方案**字段中，选择**将添加到解决方案**。  
  
6.  在**位置**字段中，验证 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common**的路径。  
  
7.  单击**确定**打开新项目。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将新项目添加到解决方案资源管理器。 它还添加项目文件夹，并创建中的文件\<*驱动器*\>: \Tutorial\\**BTAHL7V22Common**项目文件夹。  
  
8.  在解决方案资源管理器，右键单击**BTAHL7 项目**项目，指向**添加**，然后单击**新项**。  
  
9. 在添加新项-BTAHL7 项目对话框中，在**类别**窗格中，单击**架构文件**，然后在**模板**窗格中，单击**架构**.  
  
10. 在**名称**字段中，键入**Doorbell.xsd**命名架构。  
  
11. 单击**添加**若要打开 BizTalk 编辑器中的空白的架构。  
  
12. 在**\<架构\>** 树中，右键单击**根**节点，，然后单击**重命名**。  
  
13. 类型**DoorbellRoot**作为新名称，然后按**Enter**。  
  
14. 右键单击**DoorbellRoot**节点，指向**插入架构节点**，然后单击**子字段元素**添加以下字段 （每个字段重复此步骤元素）：  
  
    -   **FirstName**  
  
    -   **MiddleName**  
  
    -   **LastName**  
  
    -   **SSN**  
  
15. 在解决方案资源管理器，右键单击**BTAHL7 项目**，指向**添加**，然后单击**新项**。  
  
16. 在添加新项-BTAHL7 项目对话框中，在**类别**窗格中，单击**BTAHL7 架构**，然后单击**添加**。  
  
17. 在 HL7 架构选择器对话框中，在**消息类**框中，选择**V2.X**，然后在**架构的详细信息**窗格中，执行以下操作：  
  
    |使用此选项|動作|  
    |--------------|----------------|  
    |**版本**|选择 HL7 消息的版本号。 在本教程中，使用**2.2**。|  
    |**消息类型**|选择 HL7 消息的类型。 在本教程中，使用**ADT**。|  
    |**触发器事件**|选择 HL7 消息的触发器事件值。 在本教程中，使用**A04**。|  
  
18. 单击**完成**ADT_A04_22_GLO_DEF.xsd （注册患者） 架构添加到你的项目。 关闭 HL7 架构选择器对话框。  
  
19. 在解决方案资源管理器下**BTAHL7 项目**，右键单击**引用**，然后单击**添加引用**。  
  
20. 在添加引用对话框中，在**项目**选项卡上，选择**BTAHL7V22Common**项目中，单击**添加**，然后单击**确定**。  
  
    > [!NOTE]
    >  这将添加到原始项目引用，以便[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]正确识别 HL7 架构。  
  
21. 在解决方案资源管理器下**BTAHL7 项目**，右键单击**引用**，然后单击**添加引用**。  
  
22. 在添加引用对话框中，单击**浏览**选项卡。在**查找中**框中，移动到\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端教程中的快捷键\Tutorial_BTAHL7Drop\Bin。 单击**Microsoft.Solutions.BTAHL7.HL7Schemas.dll**，单击**添加**，然后单击**确定**。  
  
 继续执行[步骤 5： 将架构属性提升](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)