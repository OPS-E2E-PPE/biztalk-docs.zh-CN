---
title: "步骤 2： 创建新项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b296b01179b3ce52aef41dc246dbed2588c3e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-create-a-new-project"></a>步骤 2： 创建新项目
通过使用在此步骤中，生成一个新的解决方案[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]环境。 首先，创建新项目 (BTAHL7V22Common) 包含三个常见架构 （适用于数据类型、 线段和表值） 的 HL7 V2.2 架构使用，包括你将用于传出的 HL7 消息的架构。 其次，生成另一个新包含 HL7 消息 (MSH_25_GLO_DEF) 中的标头使用的常见标准架构的项目 (BTAHL7V2XCommon)。  
  
### <a name="to-create-a-new-project"></a>创建新项目的步骤  
  
1.  启动**Visual Studio**。  
  
2.  在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。  
  
3.  在新建项目对话框中，展开**BizTalk 项目**文件夹，，然后单击**BTAHL7Projects**文件夹。  
  
4.  在**模板**窗格中，单击**BTAHL7V22Common 项目**。  
  
5.  在**名称**字段中，键入**BTAHL7V22Common**作为项目名称。  
  
6.  在**位置**字段中，键入*\<驱动器\>***: \Tutorial**作为路径，然后单击**确定**以打开新的项目中。  
  
    > [!NOTE]
    >  BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将新项目添加到解决方案资源管理器中，具有三个常见架构：  
  
    -   datatypes_22.xsd  
  
    -   segments_22.xsd  
  
    -   tablevalues_22.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]创建项目文件夹和文件中\<*驱动器*\>: \Tutorial\BTAHL7V22Common 文件夹。  
  
7.  在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。  
  
8.  在新建项目对话框中，展开**BizTalk 项目**文件夹，，然后单击**BTAHL7Projects**文件夹。  
  
9. 在**模板**窗格中，单击**BTAHL7V2XCommon 项目**。  
  
10. 在**名称**字段中，键入**BTAHL7V2XCommon**作为项目名称。  
  
11. 在**位置**字段中，键入*\<驱动器\>***: \Tutorial**作为路径。  
  
12. 在**解决方案**字段中，选择**将添加到解决方案**，然后单击**确定**。  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将新项目添加到解决方案资源管理器中，具有以下架构：  
  
    -   ACK_24_GLO_DEF.xsd  
  
    -   ACK_25_GLO_DEF.xsd  
  
    -   MSH_25_GLO_DEF.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]创建项目文件夹和文件中**\<驱动器\>: \Tutorial\BTAHL7V22Common\BTAHL72XCommon**文件夹。  
  
 继续执行[步骤 3： 向程序集分配强名称](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)