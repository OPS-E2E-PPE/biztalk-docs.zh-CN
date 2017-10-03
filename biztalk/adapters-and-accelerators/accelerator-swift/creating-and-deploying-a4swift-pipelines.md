---
title: "创建和部署 A4SWIFT 管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bec21ebd5a3b32986969676a78109cad55d870cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-deploying-a4swift-pipelines"></a>创建和部署 A4SWIFT 管道
下图中所示，请执行以下步骤以创建和部署消息修复和新提交的 SWIFT 管道。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")  
  
 **摘要**  
  
 部署以下架构：  
  
-   自定义接收 SWIFT 反汇编程序与的管道。 将 BRE 验证和 XML 验证属性设置为 True，并将 SWIFT 标头架构属性为 （无）。  
  
-   自定义发送 SWIFT 汇编程序与的管道  
  
### <a name="to-create-a-pipeline-project"></a>若要创建管道项目  
  
1.  在 Visual Studio 中，单击**文件**，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**窗格中，选择**BizTalk 项目**文件夹。  
  
3.  在**模板**窗格中，选择**空 BizTalk 服务器项目**。  
  
4.  在**名称**框中，键入所需项目名称的名称。  
  
5.  在**解决方案**框中，选择**将添加到解决方案**。 在**位置**框中，输入你在中创建架构项目的位置[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。  
  
6.  单击**确定**打开新项目。  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]将新项目添加到解决方案资源管理器，并在指定的文件夹中创建的项目文件夹和文件。  
  
7.  创建并分配到项目的强密钥文件。 有关详细信息，请参阅创建具有强名称的 SWIFT 项目"的"[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。  
  
### <a name="to-add-a-custom-receive-pipeline"></a>若要添加自定义接收管道  
  
1.  在解决方案资源管理器，右键单击你的管道项目，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**从模板窗格。  
  
3.  在**名称**框中，键入管道的名称。  
  
4.  单击**添加**以 BizTalk 管道设计器中打开空白的管道。  
  
5.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**然后**工具箱**。  
  
6.  从**BizTalk 管道组件工具箱**，拖动**SWIFT 反汇编程序**到**拖至此处**下面框**拆卸**阶段在调整**BizTalk 管道设计器**。 保留**SWIFT 反汇编程序**中为选定**BizTalk 管道设计器**。  
  
7.  在**属性**，验证**BRE 验证**和**XML 验证**属性设置为**True**。  
  
    > [!NOTE]
    >  SWIFT 标头架构属性应设置为**（无）**。  
  
8.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，，然后**保存所有**。  
  
### <a name="to-add-a-custom-send-pipeline"></a>若要添加自定义，将发送管道  
  
1.  在解决方案资源管理器，右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。  
  
2.  在添加新项对话框中，确保**管道文件**是否选择在类别窗格中，然后选择**发送管道**从模板窗格。  
  
3.  在**名称**框中，键入管道的名称。  
  
4.  单击**添加**以 BizTalk 管道设计器中打开空白的管道。  
  
    > [!NOTE]
    >  在 BizTalk 管道设计器中显示空的管道。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将新管道 SWIFTPipelines 项目下添加到解决方案资源管理器中。  
  
5.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**然后**工具箱**。  
  
6.  在**BizTalk 管道组件工具箱**，拖动**SWIFT 汇编程序**到**拖至此处**下面框**装配**阶段中的形状**BizTalk 管道设计器**。  
  
7.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，，然后**保存所有**。  
  
8.  右键单击管道项目，然后单击**生成**。  
  
    > [!NOTE]
    >  在编译过程中，不应看到任何失败。 如果这样做，请检查错误的源，其更正，然后重新生成项目。 但是，可能会看到警告。 您可以更正导致警告的条件。 有关详细信息，请参阅"生成管道项目可能会导致警告"[杂项已知问题](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)。  
  
9. 右键单击管道项目，然后单击**部署**。