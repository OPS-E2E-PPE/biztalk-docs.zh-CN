---
title: 消息检查器管道组件 |Microsoft Docs
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
ms.openlocfilehash: 5a0672727823de091a71cfe7173a20851718ee3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282959"
---
# <a name="message-inspector-pipeline-component"></a>消息检查器管道组件
此管道组件可以检查多部分消息和消息上下文，以确定是否存在问题的消息的所有部分。 将该组件的故障排除。  
  
 管道组件将 XML 文件放入你指定的目录。 每个文件包含 RNIFv2.0 消息 （前导头、 传递头、 服务头和服务内容） 的四个部分或 RNIFv1.1 消息 （前导头、 服务头和服务内容） 的三个部分之一。 另一个 XML 文件包含消息上下文。  
  
 此组件构建到自定义管道，并将其附加到发送端口。 在发送端口以订阅你想要监视的消息中创建一个筛选器。 此故障排除操作除了处理该 Microsoft® 标准[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]已执行。  
  
## <a name="building-a-custom-pipeline-using-the-message-inspector-pipeline-component"></a>构建自定义管道使用消息检查器管道组件  
 若要使用消息检查器管道组件，必须生成和部署包含组件的自定义管道。 有关详细信息，请参阅"创建管道使用管道设计器"中 BizTalk Server 帮助。  
  
#### <a name="to-deploy-the-message-inspector-pipeline-component"></a>若要部署消息检查器管道组件  
  
1. 启动 Visual Studio。  
  
2. 上**文件**菜单，依次指向**打开**，然后单击**项目**。  
  
3. 将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component，选择**MessageInspector.csproj**，然后单击**打开**。  
  
4. 打开 Visual Studio 命令提示符。  
  
5. 在命令提示符处，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug。  
  
6. 在命令提示符处，键入**sn-k MessageInspector.snk"** 创建密钥，，然后按 ENTER。  
  
7. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击**MessageInspector**，然后单击**属性**。  
  
8. 在中**MessageInspector 属性**页上，单击**签名**选项卡，然后依次**程序集签名**复选框。  
  
9. 在中**选择强名称密钥文件**下拉列表中，浏览到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug 选择**MessageInspector.snk** ，然后单击**打开**。  
  
10. 在解决方案资源管理器中右键单击**MessageInspector**，然后单击**生成**。 在输出窗格中验证生成成功。  
  
11. 单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**Windows 资源管理器**。  
  
12. 在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message Inspector Pipeline Component\obj\debug，右键单击**Microsoft.Solutions.BTARN.SDK.MessageInspector.dll**，然后单击**复制**。  
  
13. 将移到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Pipeline Components，右键单击**管道组件**，然后单击**粘贴**.  
  
14. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  
  
15. 在中**新的项目**对话框中，在模板窗格中，选择**空的 BizTalk Server 项目**，在**名称**框中，键入项目的名称。 在中**位置**框中，转到你想要保存在中，项目的文件夹，然后单击**确定**。  
  
16. 在解决方案资源管理器中右键单击项目名称，指向**外**，然后单击**添加新项**。  
  
17. 在中**添加新项**对话框中，选择**发送管道**，在**名称**框中，为自定义管道文件中，键入一个名称，然后单击**打开**.  
  
    > [!NOTE]
    >  添加消息检查器管道组件只是为了发送端口，不能接收端口。  
  
18. 在工具箱窗格中，在 BizTalk 管道组件窗格中右键单击，然后单击**添加/删除项**。  
  
19. 在**自定义工具箱**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTARN 消息检查器组件**，然后单击**确定**.  
  
20. 在工具箱窗格的 BizTalk 管道组件窗格中，单击并按住**BTARN 消息检查器组件**，然后将该组件拖动上**放到此处 ！** 框。  
  
21. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击管道项目的名称，然后单击**属性**。  
  
22. 在中**属性页**对话框中，单击**通用属性**，然后单击**程序集**。  
  
23. 在右窗格中，在文本框中与相关联**程序集密钥文件**，单击省略号，转到 C:\Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Message InspectorPipeline Component\obj\debug，选择**MessageInspector.snk**，然后单击**确定**。  
  
24. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]管道设计器中，选择**BTARN 消息检查器组件**形状。  
  
25. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]属性窗口，请在**Directory**框中，键入你想要删除的 XML 文件的目录的名称。  
  
26. 在解决方案资源管理器，右键单击项目名称，然后单击**生成**。 验证成功生成。  
  
27. 在解决方案资源管理器，右键单击项目名称，然后单击**部署**。 验证部署成功。  
  
28. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**视图**菜单中，单击**BizTalk 浏览器**。  
  
29. 右键单击**发送端口**，然后单击**添加发送端口**。  
  
30. 在中**创建新发送端口**对话框中，单击**确定**。  
  
31. 在中**发送端口属性**对话框中**名称**框中，键入发送端口的名称与**主**选择左窗格中，单击**传输类型**右窗格中，然后选择**文件**。  
  
32. 在中**发送端口属性**对话框中**地址 (URI)** 框中，单击省略号按钮 (**...**).  
  
33. 在中**FILE 传输属性**对话框中，键入**目标**文件夹的名称，单击**发送**在左窗格中，然后为**发送管道**在右窗格中，选择刚创建的自定义管道。  
  
34. 单击**筛选器和映射**在左窗格中，然后单击**筛选器**。  
  
35. 在右窗格中，用于指定你想要删除的 XML 文件的管道文件的类型中输入筛选器表达式。 例如，如果你想要删除的文件为所有 RNIF v1.1 消息**属性**应选择 Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction，并为**运算符**像选择"Exists"，然后单击**确定**。  
  
36. 在 BizTalk 浏览器中，右键单击刚创建的发送端口，单击**登记**，同样，右键单击发送端口，然后单击**启动**。  
  
## <a name="remarks"></a>备注  
 在典型处理中，你只能检查消息的部分之一一次 （已指定为业务流程中消息正文的部分）。 因此，你只能检查在 BizTalk 管理控制台中，部分之一并排除故障的能力是有限。 消息检查器管道组件可帮助你克服此限制。  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
