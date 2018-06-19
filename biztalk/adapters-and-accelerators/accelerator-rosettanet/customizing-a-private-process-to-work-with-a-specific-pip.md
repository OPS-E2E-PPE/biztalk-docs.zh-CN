---
title: 自定义以使用特定 PIP 私有过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f84cd2de6d5f79062592dbf71947587b6d7a6ff0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966747"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a>自定义以使用特定 PIP 私有过程
你可以创建特定的筛选器表达式，使响应方专用业务流程处理或不处理特定合作伙伴接口流程 (PIP) 的实例。 这样你就可以灵活地创建自定义专用流程来接收和处理某些 PIP 实例，而使用默认的专用流程来处理所有其他 PIP 实例。  
  
 若要创建自定义专用流程以处理一个或多个特定 PIP，可为专用业务流程的接收形状创建筛选器表达式。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 中提供了一个示例：PIP3A4PrivateResponder.odx 业务流程。 它位于\<*驱动器*\>: \Program Files\BizTalk\<版本\>RosettaNet\SDK\PIP3A4Process 使用业务 Rules\PIP3A4PrivateResponder 快捷键。  
  
 除创建只处理特定 PIP 实例的专用流程外，还必须自定义默认的 BTARN 专用流程，使其不处理该 PIP 的实例。  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a>自定义处理特定 PIP 的响应方专用流程  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 中，创建处理特定 PIP 的自定义响应方专用业务流程。 可以基于默认的 BTARN 响应方专用业务流程来创建该业务流程。  
  
    > [!NOTE]
    >  你可以在 BTARN SDK 中查找默认的响应方专用业务流程，其名称为 PrivateResponder.odx。 它位于*\<驱动器\>*: \Program Files\BizTalk\<版本\>RosettaNet\SDK\PrivateResponder 快捷键。  
  
2.  将该自定义业务流程添加到 BizTalk 项目中。 确保该项目中具有对 Microsoft.Solutions.BTARN.GlobalSchemas.dll 文件的引用。  
  
3.  在业务流程设计器中打开该自定义业务流程。  
  
4.  右键单击第一个**接收**形状，激活业务流程，然后单击**编辑筛选器表达式**。  
  
    > [!NOTE]
    >  默认 BTARN 响应方私有进程业务流程的接收形状具有两个筛选器条件： Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="AsyncAction"或 Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="SyncAction"。 此表达式确保该业务流程处理 RosettaNet 消息。 请在自定义业务流程中保留此筛选器表达式。  
  
5.  在**筛选器表达式**对话框中，在第一个打开行中，属性列中的选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表中，在运算符列中，选择 **==** 从下拉列表中，在值列中，键入的三个数字 PIP 代码，例如，键入**3A4**。  
  
6.  单击 **“确定”**。  
  
7.  在业务流程设计器中打开默认的响应方专用业务流程项目 (PrivateResponder.btproj)。 确保在该项目中具有对 Microsoft.Solutions.BTARN.GlobalSchemas.dll 文件的有效引用。  
  
8.  双击**PrivateResponder.odx**。  
  
9. 右键单击**ReceiveFromPublicProcessResponder**接收形状，并依次**编辑筛选器表达式**。  
  
10. 在**筛选器表达式**对话框中，在第一个打开行中，属性列中的选择**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**从下拉列表。 在运算符列中，选择 **！ =** 从下拉列表。 在值列中，键入三位数 PIP 代码，例如，键入"**3A4"**。  
  
11. 单击 **“确定”**。  
  
12. 在解决方案资源管理器，右键单击包含业务流程的项目，然后单击**生成**。  
  
13. 已成功生成项目后，右键单击该项目，然后单击**部署**。  
  
14. 上**文件**菜单上，指向**打开**，然后单击**项目**。  
  
15. 将移动到\<*驱动器*\>: \Program Files\BizTalk\<版本\>Accelerator for RosettaNet\SDK\PrivateResponder，选择**PrivateResponder.odx**，然后单击**确定**。  
  
16. 在解决方案资源管理器中，右键单击该项目，再单击“生成”。  
  
17. 已成功生成项目后，右键单击该项目，然后单击**部署**。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)