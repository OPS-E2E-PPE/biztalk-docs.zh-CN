---
title: How to Create for XML 消息的架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6396d4607e93298961e6691ded2ca8d4566d819c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25969723"
---
# <a name="how-to-create-schemas-for-xml-messages"></a>如何为 XML 消息创建架构
有多种方法用于创建 BizTalk 消息架构。 本主题提供这些方法的某些的分步说明。  
  
### <a name="to-create-a-new-schema"></a>若要创建新的架构  
  
1.  在 **解决方案资源管理器**, ，选择你想要添加的架构的 BizTalk 项目。  
  
2.  在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
3.  在**添加新项- \< *BizTalk ProjectName* \>** 对话框中，在**模板**部分中，单击**架构**.  
  
4.  在 **名称** 框中，为架构中，键入一个名称，然后单击 **添加**。  
  
5.  如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。  
  
6.  在架构树视图中，选择 **架构** 节点，然后在属性窗口中，选择 **目标 Namespace** 属性和类型的目标命名空间的名称。 务必将此属性设置在此初始阶段中的架构创建;避免使用默认值 **目标 Namespace** 属性值。  
  
    > [!NOTE]
    >  项目成员文件，例如架构文件，某些名称选项可以与 C# 保留字和.net Framework 类型和命名空间名称 （如系统） 导致更高版本在由于冲突而进行的编译错误。 例如以下架构名称：schema.xsd、XmlContent 和 RootNodes。 这是因为 **类型名称** 属性默认为的基 （非扩展） 部分  **Filename** 属性。 可以通过显式更改的值来解决这种类型的编译错误 **类型名称** 某事不冲突的属性。  
  
    > [!NOTE]
    >  你可能需要添加、 删除和修改的记录和及其关联的属性以及架构中的字段。 若要了解详细信息，请参阅[管理架构节点内](../core/managing-the-nodes-within-a-schema.md)。  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a>若要从非 XSD 源生成架构  
  
1.  在 **解决方案资源管理器**, ，右键单击 BizTalk 项目，指向 **添加**, ，然后单击 **添加生成的项**。  
  
2.  在**添加生成的项的\< *BizTalk ProjectName* \>** 对话框中，在**模板**部分中，单击**生成架构**，然后单击**添加**。  
  
3.  在 **生成架构** 对话框中，在 **文档类型** 下拉列表中，选择 **XDR 架构**, ，**DTD 架构**, ，或 **格式正确 XML**。  
  
     如果你看到任何一个 **DTD （未加载）** 或 **（未加载） 的格式正确 XML** 在下拉列表中，仍，选择适当的文档类型，然后你将指导您完成安装缺少的 DLL 的过程。 然后，重复这些步骤。  
  
4.  在 **生成架构** 对话框中，单击 **浏览**, ，找到你想要导入，然后单击的文件 **打开**。 你找到该文件必须与你在上一步中选择文档类型匹配。  
  
     从指定的文件，使用相同的名称作为扩展名为.xsd，该文件，并在 BizTalk 编辑器中打开生成新的架构。  
  
## <a name="see-also"></a>另请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)