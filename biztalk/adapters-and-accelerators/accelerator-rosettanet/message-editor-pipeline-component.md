---
title: 消息编辑器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b010f9f1e8a1217e2928ef4cfd147b56bf7043
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283208"
---
# <a name="message-editor-pipeline-component"></a>消息编辑器管道组件
此组件可自动编辑任何部分的多部分消息中发送或接收管道。 向现有管道设置替换的典型处理部分添加此组件。  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a>在现有管道中构建消息编辑器管道组件  
 若要使用消息编辑器管道组件，您必须向现有管道添加组件。 有关详细信息，请参阅"创建管道使用管道设计器"中 BizTalk Server 帮助。  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a>若要向现有管道添加消息编辑器管道组件  
  
1. 启动 Visual Studio。  
  
2. 上**文件**菜单，依次指向**打开**，然后单击**项目**。  
  
3. 将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Editor Pipeline Component，选择**MessageEditor.csproj**，然后单击**打开**.  
  
4. 启动 Visual Studio 命令提示符。  
  
5. 在命令提示符处，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug。  
  
6. 在命令提示符处，键入**sn-k MessageEditor.snk**创建密钥，，然后按 ENTER。  
  
7. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**MessageEditor**，然后单击**属性**。  
  
8. 在中**MessageEditor 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。  
  
9. 在中**选择强名称密钥文件**下拉列表中，浏览到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for Rosettanet\sdk\message Editor Pipeline Component\obj\debug 选择**MessageEditor.snk** ，然后单击**打开**。  
  
10. 在解决方案资源管理器中右键单击**MessageEditor**，然后单击**生成**。 在输出窗格中验证生成成功。  
  
11. 单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
12. 在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug，右键单击**Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**，然后单击**复制**。  
  
13. 转到 C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components，右键单击**管道组件**，然后单击**粘贴**。  
  
14. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**打开**，然后单击**项目**。  
  
15. 打开包含你想要添加编辑器的管道的项目。  
  
16. 在解决方案资源管理器，双击要在管道设计器中打开该管道的管道名称。  
  
17. 在工具箱窗格中，BizTalk 管道组件窗格中右键单击，然后单击**添加/删除项**。  
  
18. 在**自定义工具箱**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTARN 消息编辑器组件**，然后单击**确定**.  
  
19. 在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息编辑器组件**，然后将该组件拖动到要在管道中的位置。  
  
20. 在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息编辑器组件**，然后将该组件拖动到要在管道中的位置。  
  
    > [!NOTE]
    >  建议在接收管道组件或发送管道组件的预组装阶段中的拆装阶段后添加消息编辑器管道组件。  
  
21. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在管道设计器中，选择**BTARN 消息编辑器组件**形状。  
  
22. 在属性窗格中，在文本框中与相关联**XPath 查询**，键入你想要更改的值的 XPath 元素的名称。  
  
23. 在文本框中与相关联**XPath 值**，键入你想要设置的 XPath 元素的值。  
  
24. 在解决方案资源管理器中，右键单击项目名称，然后单击**生成**。 验证成功生成。  
  
25. 在解决方案资源管理器中，右键单击项目名称，然后单击**部署**。 验证部署成功。  
  
## <a name="example"></a>示例  
 若要更改元素的值`ProprietaryDocumentIdentifier`中 0c1 PIP 架构添加到消息编辑器管道组件的 XPath 查询属性在以下代码部分中所示的 XPath 查询。  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 若要获取完整的 XPath 查询，打开在 BizTalk 编辑器中的架构，并复制从 Xpath`Instance XPath`下属性窗口的属性。 你提供的 XPath 查询应包含所有命名空间引用。  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
