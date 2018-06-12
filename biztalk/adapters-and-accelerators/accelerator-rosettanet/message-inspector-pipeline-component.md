---
title: 消息检查器管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, custom pipelines
- pipelines, Message Inspector Pipeline Component
- Message Inspector Pipeline Component
- pipelines, creating
ms.assetid: d9c00718-c8cd-4289-8f58-e4edc61b9a05
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb6b8a2d9bcd503b1b295110665827ead3e85ee6
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855616"
---
# <a name="message-inspector-pipeline-component"></a>消息检查器管道组件
使用此管道组件，你可以检查由多个部分组成的消息的所有部分和消息上下文，以便确定消息是否存在问题。 你可以用此组件来排除故障。  
  
 该管道组件将 XML 文件放入你指定的目录中。 这些文件中的每一个都包含 RNIFv2.0 消息的四个部分（前导头、传递头、服务头和服务内容）中的一个或 RNIFv1.1 消息的三个部分（前导头、服务头和服务内容）中的一个。 另一个 XML 文件中包含消息上下文。  
  
 你可以将此组件构建到自定义管道中，然后将其附加到发送端口。 你可以在发送端口中创建一个筛选器，用于订阅要监视的消息。 除了 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 已执行的标准处理操作外，还可以执行此故障排除操作。  
  
## <a name="building-a-custom-pipeline-using-the-message-inspector-pipeline-component"></a>使用消息检查器管道组件构建自定义管道  
 若要使用消息检查器管道组件，你必须构建并部署一个包含该组件的自定义管道。 有关详细信息，请参阅"创建管道与管道中的设计器"BizTalk Server 帮助。  
  
#### <a name="to-deploy-the-message-inspector-pipeline-component"></a>部署消息检查器管道组件  
  
1.  启动 Visual Studio。  
  
2.  上**文件**菜单上，指向**打开**，然后单击**项目**。  
  
3.  将移动到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message 检查器管道组件，选择**MessageInspector.csproj**，然后单击**打开**。  
  
4.  打开 Visual Studio 命令提示符。  
  
5.  在命令提示符下，将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK\Message 检查器管道 Component\obj\debug 快捷键。  
  
6.  在命令提示符处，键入 **"sn-k MessageInspector.snk"** 创建密钥，，然后按 enter 键。  
  
7.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击**MessageInspector**，然后单击**属性**。  
  
8.  在**MessageInspector 属性**页上，单击**签名**选项卡上，并依次**对程序集签名**复选框。  
  
9. 在**选择强名称密钥文件**下拉列表中，浏览到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK\Message 检查器管道 Component\obj\debug 和选择的快捷键**MessageInspector.snk** ，然后单击**打开**。  
  
10. 在解决方案资源管理器中，右键单击**MessageInspector**，然后单击**生成**。 在输出窗格中检验该生成操作是否成功。  
  
11. 单击**启动**，指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
12. 在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，移动到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message 检查器管道 Component\obj\debug，右键单击**Microsoft.Solutions.BTARN.SDK.MessageInspector.dll**，然后单击**复制**。  
  
13. 将移动到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Pipeline 组件，右键单击**管道组件**，然后单击**粘贴**.  
  
14. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
15. 在**新项目**对话框中，在模板窗格中，选择**空 BizTalk 服务器项目**中**名称**框中，键入项目的名称。 在**位置**框中，将移动到你想要保存在中，项目的文件夹，然后单击**确定**。  
  
16. 在解决方案资源管理器，右键单击项目名称，指向**添加**，然后单击**添加新项**。  
  
17. 在**添加新项**对话框中，选择**发送管道**中**名称**框中，为自定义管道文件中，键入一个名称，然后单击**打开**.  
  
    > [!NOTE]
    >  请只将消息检查器管道组件添加到发送端口，而不要添加到接收端口。  
  
18. 在工具箱窗格中，BizTalk 管道组件窗格中右键单击，然后单击**添加/删除项**。  
  
19. 在**自定义工具箱**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTARN 消息检查器组件**，然后单击**确定**.  
  
20. 在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息检查器组件**，然后将该组件拖动上**拖至此处 ！** 框。  
  
21. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击该管道项目的名称，然后单击**属性**。  
  
22. 在**属性页**对话框中，单击**通用属性**，然后单击**程序集**。  
  
23. 在右窗格中，与关联的文本框中**程序集密钥文件**，单击省略号，将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message 检查器管道 Component\obj\debug，选择**MessageInspector.snk**，然后单击**确定**。  
  
24. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]管道设计器中，选择**BTARN 消息检查器组件**形状。  
  
25. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]属性窗口，请在**目录**框中，键入你想要删除的 XML 文件的目录的名称。  
  
26. 在解决方案资源管理器，右键单击项目名称，然后单击**生成**。 检验该生成操作是否成功。  
  
27. 在解决方案资源管理器，右键单击项目名称，然后单击**部署**。 检验该部署操作是否成功。  
  
28. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**视图**菜单上，单击**BizTalk 资源管理器**。  
  
29. 右键单击**发送端口**，然后单击**添加发送端口**。  
  
30. 在**创建新发送端口**对话框中，单击**确定**。  
  
31. 在**发送端口属性**对话框中，在**名称**框中，键入发送端口的名称与**主**选择左窗格中，单击**传输类型**在右窗格中，选择**文件**。  
  
32. 在**发送端口属性**对话框中，在**地址 (URI)** 框中，单击省略号按钮 (**...**).  
  
33. 在**文件传输属性**对话框中，键入**目标**文件夹名称，单击**发送**在左窗格中，然后为**发送管道**在右窗格中，选择刚创建的自定义管道。  
  
34. 单击**筛选器和映射**在左窗格中，然后单击**筛选器**。  
  
35. 在右窗格中输入筛选器表达式，指定希望该管道为哪种类型的文件放置 XML 文件。 例如，如果你想要删除的文件的所有 RNIF v1.1 消息，**属性**会选择 Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction，和**运算符**像选择"Exists"，然后单击**确定**。  
  
36. 在 BizTalk 资源管理器中，右键单击你刚刚创建的发送端口，请单击**Enlist**，再次右键单击发送端口，，然后单击**启动**。  
  
## <a name="remarks"></a>Remarks  
 在常规的处理操作中，你一次只能检查消息的一部分，即已在业务流程中指定为消息正文的部分。 因此，你只能在 BizTalk 管理控制台中检查消息的各个部分中的一个，这样，排除故障的能力就受到限制。 消息检查器管道组件可以帮助你突破此限制。  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
