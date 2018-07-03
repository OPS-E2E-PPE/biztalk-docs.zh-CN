---
title: 如何为 XML 消息创建架构 |Microsoft Docs
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
ms.openlocfilehash: a22b241d002884f24be0a2972db24b8a398ee1d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984446"
---
# <a name="how-to-create-schemas-for-xml-messages"></a>如何为 XML 消息创建架构
有几种方法用于创建 BizTalk 消息架构。 本主题提供一些方法的分步说明。  
  
### <a name="to-create-a-new-schema"></a>若要创建新的架构  
  
1. 在中**解决方案资源管理器**，选择你想要添加的架构的 BizTalk 项目。  
  
2. 在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
3. 在中**添加新项- \< *BizTalk 项目名称*\>** 对话框中，在**模板**部分中，单击**架构**.  
  
4. 在中**名称**框中，键入架构的名称，然后单击**添加**。  
  
5. 如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。  
  
6. 在架构树视图中，选择**架构**节点，然后在属性窗口中，选择**Target Namespace**属性并键入目标命名空间的名称。 务必将此属性设置在此初始阶段中的架构创建;避免使用默认值**目标 Namespace**属性值。  
  
   > [!NOTE]
   >  某些项目成员文件，例如架构文件的名称选项可能会导致编译错误由于冲突而进行更高版本上使用 C# 保留字和.net Framework 类型和命名空间名称 （例如系统）。 例如以下架构名称：schema.xsd、XmlContent 和 RootNodes。 这是因为**类型名称**属性默认为基 （非扩展名） 部分**Filename**属性。 可以通过显式更改的值来解决这种类型的编译错误**类型名称**为不冲突的属性。  
  
   > [!NOTE]
   >  您可能需要添加、 删除和修改的记录和字段以及其关联的属性架构中。 若要了解详细信息，请参阅[管理架构节点内](../core/managing-the-nodes-within-a-schema.md)。  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a>若要从非 XSD 源生成架构  
  
1.  在中**解决方案资源管理器**，右键单击 BizTalk 项目，依次指向**添加**，然后单击**添加生成的项**。  
  
2.  在中**添加生成的项- \< *BizTalk 项目名称*\>** 对话框中，在**模板**部分中，单击**生成架构**，然后单击**添加**。  
  
3.  在中**生成架构**对话框中**文档类型**下拉列表中，选择**XDR 架构**， **DTD 架构**，或**格式正确的 XML**。  
  
     如果看到任何一个**DTD （未加载）** 或**格式正确的 XML （未加载）** 在下拉列表中，选择相应的文档类型，并完成安装过程将指导你缺少 DLL。 然后，重复这些步骤。  
  
4.  在中**生成架构**对话框中，单击**浏览**，找到你想要导入，然后单击的文件**打开**。 您找到该文件必须匹配你在上一步中选择的文档类型。  
  
     从指定的文件，使用相同的名称作为该文件扩展名为.xsd 和 BizTalk 编辑器中打开生成新的架构。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)