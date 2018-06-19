---
title: 扩展与新 PIP BTARN |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, extending functionality
- PIPs, extending BTARN
- BTARN, PIPs
ms.assetid: 3db5cd5c-031f-4451-9be5-4b5d6163c3b1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b1fca61cd40b932e53b2908603a225d3980fa1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007162"
---
# <a name="extending-btarn-with-a-new-pip"></a>扩展与新 PIP BTARN
本主题介绍如何扩展[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]与新的合作伙伴接口过程 (PIP) 架构。 这使你能够在 RosettaNet PIP 不与 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装程序所安装的任何架构相关联时，基于该 PIP 添加架构。  
  
 在使用新 PIP 扩展 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 时，请将新架构部署在其自己的程序集中。 还可以修改部署到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIP 程序集内的现有架构。 有关详细信息，请参阅[修改现有 PIP 在 RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)。  
  
### <a name="to-extend-btarn-with-a-new-pip"></a>使用新 PIP 扩展 BTARN  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for RosettaNet\SDK\Utilities\Schema 生成器。  
  
3.  在命令提示符处，键入**CScript InstallDTD.vbs**，然后按**Enter**。  
  
    > [!NOTE]
    >  你将仅需要在安装 BizTalk Server 之后一次执行步骤 1 到 3。  
  
4.  启动 Visual Studio。  
  
5.  在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。  
  
6.  在新建项目对话框中，选择**BizTalk 项目**在左窗格中，然后单击**空 BizTalk 服务器项目**右窗格中。  
  
7.  单击**浏览**和指向你想要保存你的项目的目录。  
  
8.  在**名称**框中，键入项目名称，如**MyCustomPIP**，然后单击**确定**。  
  
9. 启动 Visual Studio 命令提示符。  
  
10. 在命令提示符下，移动到在步骤 7，类型中输入的位置**sn-k\<项目 name.snk\>**，然后按**Enter**。  
  
11. 在解决方案资源管理器中，右键单击项目名称，然后单击**属性**。  
  
12. 在**属性页**对话框中，单击**程序集**下**通用属性**的左窗格中。  
  
13. 在右窗格中，向下滚动到**强名称**，单击**程序集密钥文件**，然后单击右窗格中的省略号按钮 （...）。 转到在步骤 7 中输入的位置，然后选择在步骤 10 中创建的 .snk 文件的名称。  
  
14. 在属性页对话框中，展开**配置属性**，然后单击**部署**。 在右窗格中，单击**重新部署**，选择`True`，然后单击**确定**。  
  
15. 在解决方案资源管理器，右键单击项目名称，指向**添加**，然后单击**现有项**。  
  
16. 在**添加现有项**对话框中，移动到\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for RosettaNet\SDK\Schemas，选择**xml.xsd**，然后单击**添加**。  
  
17. 下载将用 RosettaNet.org 扩展 RNPIP 的 PIP。有关详细信息，请参阅[合并新的合作伙伴接口进程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)。  
  
18. 在解决方案资源管理器，展开项目名称，右键单击**引用**，然后单击**添加引用**。  
  
19. 在**添加引用**对话框中，单击**浏览**，并将移至\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk 2013 Accelerator for RosettaNet\Bin，，然后选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**。 单击**打开**，然后单击**确定**。  
  
20. 在解决方案资源管理器，右键单击项目名称，指向**添加**，然后单击**添加生成的项**。  
  
21. 在**添加生成的项**对话框中，在**类别**窗格中，单击**生成架构**。 在**模板**窗格中，单击**生成架构**，然后单击**添加**。  
  
22. 在“生成架构”对话框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档类型**|选择**DTD 架构**。|  
    |**输入的文件**|单击**浏览**，将移动到包含从 RosettaNet.org 的 DTD 文件的文件夹，选择的 DTD 文件，然后单击**打开**。|  
  
23. 在生成架构对话框中，单击**确定**。  
  
24. 在解决方案资源管理器中，双击刚导入的 .xsd 文件。  
  
25. 在 BizTalk 编辑器中，选择\<*架构*\>节点。  
  
26. 在属性窗口中，向下滚动到**文档类型**。 在**文档类型**框中， **PIP**\<*三位数代码*\>，例如， **PIP3A2**。 在**文档版本**框中，键入**v**\<*xx.xx* \>或**R** \< *xx.xx*\>，例如， **R01.02**。 此版本应与 RosettaNet PIP 规范中指定的版本相同。  
  
27. 在属性窗口中，向下滚动到**根引用**。 单击**根引用**，然后从下拉列表中，选择的架构，例如，选择的根节点**Pip3C5BillingStatementNotification**。  
  
28. 在属性窗口中，向下滚动达**目标 Namespace**。 有关**目标 Namespace**，类型**http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD 文件名\>.dtd**，其中的 DTD 文件名称是，例如， **3C5_MS_R01_00_BillingStatementNotification.dtd**。  
  
    > [!NOTE]
    >  对于 BTARN，要求目标命名空间采用这种命名约定。 如果你使用另一个命名空间约定，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将不会处理架构验证的 PIP 文档。  
  
    > [!NOTE]
    >  目标命名空间属性中的 DTD 文件名包括 PIP 的版本号。 这使你能够使用同一 PIP 代码的多个版本。  
  
29. 在属性窗口中，向下滚动达**导入**。 单击旁边的省略号按钮 （...）**导入**，然后单击**添加**。  
  
30. 在**BizTalk 类型选取器**对话框框中，展开\<*项目名称*\>，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，展开**架构**，选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**，单击**确定**，然后单击**确定**试。  
  
31. 右键单击项目名称，并依次**部署**。  
  
32. 单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
33. 在 BizTalk 管理控制台中，展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，然后展开**主机**。 下**主机**，单击**BizTalkServerApplication**。  
  
34. 在右窗格中，右键单击该主机的名称，然后单击**重新启动**。  
  
    > [!NOTE]
    >  使用新导入的 PIP 扩展 RNPIP 后，必须在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中创建正确的 PIP 配置和使用该 PIP 的协议。  
  
## <a name="see-also"></a>另请参阅  
 [合并新的合作伙伴接口进程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)   
 [使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [修改 RNPIP 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)