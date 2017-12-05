---
title: "为私有进程业务流程中定义的业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- vocabularies, saving
- private processes, orchestrations
- business rules, private processes
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- policies, deploying
- vocabularies, creating
- orchestrations, private-process orchestrations
- private processes, customizing
- policies, publishing
- business rules, Set elements
- creating, policies
- customizing private processes
- Set elements
- business rules, orchestrations
- publishing, vocabularies
- vocabularies, publishing
- creating, rules
- business rules, Get elements
- policies, saving
- publishing, policies
- Get elements
- orchestrations, business rules
- rules
- private processes, business rules
- policies, creating
ms.assetid: 5d2b0257-1b15-482b-a562-798b808e9a2d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dd0ebb22bcf6253604e4e8bf7fd858deb776b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a>为私有进程业务流程中定义的业务规则
你可以定义确认专用流程中使用的业务规则。 这使你可以动态修改业务规则，而无须停止专用业务流程。 此过程使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 业务规则引擎， 它包括以下步骤：  
  
1.  添加新词汇。 此步骤需要定义至少一个词汇常数值。 此常数值设置业务规则阈值。 此步骤还包括定义 XML 文档的 `Get` 和 `Set` 元素。 这将确定如何[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]使用阈值。  
  
2.  添加新策略。 此步骤涉及创建策略、创建一套规则，然后保存、发布和部署该策略。  
  
3.  从专用业务流程中调用该业务规则。 这涉及到添加**调用规则**形状上的与业务流程。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括一个示例，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]业务策略、 samplebtarnpolicy.xml，在\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\PipAutomation\3A4 快捷键。 有关详细信息，请参阅[示例 BTARN 业务策略](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)。  
  
 PIP3A4PrivateResponder.odx 业务流程是一个示例专用业务流程，该业务流程演示如何实现合并了业务规则的特定于合作伙伴接口流程 (PIP) 的响应方专用流程。 有关此示例的详细信息，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。  
  
 有关的词汇和策略的详细信息，请参阅 BizTalk Server 中的"开发与业务规则"主题。  
  
### <a name="to-add-a-new-vocabulary"></a>添加新词汇  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。  
  
2.  如果**打开规则存储**对话框打开，请选择**BizTalk 规则引擎**数据库，你设置在当前服务器上，然后单击**确定**。  
  
3.  在[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]业务规则编辑器，事实数据资源管理器窗格中，右键单击**词汇**，然后单击**添加新词汇**。  
  
4.  在属性窗格中 （左下角），设置**名称**属性设置为适当的词汇和然后按名称**Enter**。  
  
5.  展开你刚创建的词汇文件夹，右键单击**（不保存） 1.0 版**，然后单击**添加新定义**。  
  
6.  上**词汇定义向导**页上，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。  
  
7.  上**常量值、 值的范围或设置的值**页上，在**定义名称**框中，键入的名称的相应的词汇常量值，如**允许的最大数量**，然后单击**下一步**。  
  
8.  上**定义的常量值**页上，在**值字段**框中，键入阈值，，然后单击**完成**。  
  
### <a name="to-define-get-and-set-elements"></a>定义 Get 和 Set 元素  
  
1.  在业务规则编辑器，在事实数据资源管理器窗格中，在中"若要添加新的词汇过程"，创建的词汇文件夹下右键单击**（不保存） 1.0 版**，然后单击**添加新定义**.  
  
2.  上**词汇定义向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。  
  
3.  上**XML 文档元素或属性**页上，在定义名称文本框中，键入的名称**获取**元素。  
  
4.  单击**浏览**，移到你想要使用，选择的架构文件，然后单击的架构的位置**打开**。  
  
5.  如果**选择根节点**页打开时，选择要浏览的根节点。  
  
6.  上**选择绑定**页上，将移动到你想要将阈值定义的字段，然后单击**确定**。  
  
7.  在**文档类型**框中，键入文档名称。  
  
8.  在**操作类型**部分中，选择**执行"Get"操作**。  
  
9. 单击 **“完成”**。  
  
10. 重复上述步骤以定义一个或多个`Set`操作中，选择**执行"设置"操作**为**操作类型**。  
  
### <a name="to-save-and-publish-the-vocabulary"></a>保存和发布词汇  
  
1.  在业务规则编辑器，在你创建的词汇文件夹下的事实数据资源管理器窗格中，右击**（不保存） 1.0 版**，然后单击**保存**。  
  
2.  在事实数据资源管理器窗格中的在 3A4PurchaseOrderVocabulary 文件夹，右键单击**版本 1.0**，然后选择**发布**。  
  
### <a name="to-add-a-new-policy-and-rules"></a>添加新策略和规则  
  
1.  在业务规则编辑器，在策略资源管理器窗格中，右击**策略**，然后单击**添加新策略**。  
  
2.  单击**策略 1**。  
  
3.  在属性窗格中，设置**名称**到相应的策略名称的属性。  
  
4.  对于新策略，文件夹下的策略资源管理器窗格中右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。  
  
5.  单击**规则 1**。  
  
6.  在属性窗格中，设置**名称**想，规则名称的属性，然后按**Enter**。  
  
7.  规则编辑器中，在下**如果**窗格中，右键单击**条件**，然后选择逻辑的条件，如果适用。  
  
8.  在事实数据资源管理器窗格中，在**词汇**，展开**谓词**，展开**版本 1.0-发布**，选择你想，将其拖到编辑器图面，的谓词然后将它放在**条件**运算符或逻辑运算符。  
  
9. 在事实数据资源管理器窗格中的在词汇文件夹，展开你创建的词汇，展开**版本 1.0-发布**，选择`Get`或`Set`元素，将其拖到编辑器图面，并将其放在**argument1**。  
  
10. 词汇文件夹下，选择`Get`或`Set`元素，将其拖到编辑器图面，并将其放在**argument2**。  
  
11. 词汇文件夹下，选择`Set`元素，将其拖到编辑器图面，并将其放**操作**框然后窗格中。  
  
12. 如果变量关联`Set`元素中，单击该变量，根据需要，进行更改，然后按**Enter**。 需要的话，对其他 `Set` 元素重复该步骤。  
  
### <a name="to-save-publish-and-deploy-the-policy"></a>保存、发布并部署策略  
  
1.  完成后在业务规则编辑器中的规则，定义你创建的策略文件夹下的策略资源管理器窗格中，右键单击**（不保存） 1.0 版**，然后单击**保存**。  
  
2.  在你创建的策略文件夹下的策略资源管理器窗格中，右键单击**版本 1.0**，然后单击**发布**。  
  
3.  在你创建的策略文件夹下的策略资源管理器窗格中，右键单击**版本 1.0**，然后单击**部署**。  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a>从业务流程调用业务规则  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  上**文件**菜单上，指向打开，，然后单击**项目/解决方案**。  
  
3.  找到包含你必须调用中的业务规则，然后单击的业务流程的解决方案**打开**。  
  
4.  单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。  
  
5.  展开**变量**。 确保业务流程变量列表中包含分别与特定业务策略中每个参数相对应的变量，该特定业务策略是要从该业务流程调用的业务策略， 同时确保变量与策略参数具有相同的类型。 如果列表不包含每个策略参数的业务流程变量，请右键单击**变量**，然后单击**新变量**。 在“业务流程视图”中，键入变量名，然后在“属性”窗口中输入该参数的类型。  
  
6.  从**工具箱**，拖动**调用规则**形状变为业务流程设计图面，并将它下放**接收**形状。  
  
7.  双击**调用规则**形状。  
  
8.  在**选择你想要调用的业务策略**框中，从下拉列表中选择业务策略。  
  
9. 所示，为第一个参数为**参数名称**，从下拉列表选择一个名称。  
  
    > [!NOTE]
    >  BTARN 填充**策略参数**使用业务策略中的所有参数的列表。 对于列表中每个参数，BTARN 进入中的值**参数类型**从业务策略。 与关联的下拉列表中**参数名称**，BTARN 进入从已与策略参数的类型相同的业务流程的变量列表的所有变量的名称。 通过选择业务流程变量，可以将该变量与策略参数相关联。 你可以在“业务流程视图”中查看业务流程变量。  
  
10. 对所有其他参数重复步骤 9。  
  
11. 在业务流程设计窗口中，输入所需的业务策略，包括添加与关联的处理的所有其他形状**决策**下调整**调用规则**形状。  
  
    > [!NOTE]
    >  有关如何使用的示例**调用规则**形状中业务流程，请参阅 BTARN SDK 中包含 PIP3A4PrivateResponder.odx 业务流程。 它位于\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\PipAutomation\3A4\PR 快捷键。 有关详细信息，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。  
  
12. 单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [示例 BTARN 业务策略](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [使用业务规则的 3A4 专用响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)