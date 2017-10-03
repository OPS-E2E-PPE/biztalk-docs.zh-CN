---
title: "步骤 1： 添加标头和确认架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b5fb871bed9f6a4f54261db7e54587c65244344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a>步骤 1： 添加标头和确认架构
在此步骤中，你可以创建基于 BTAHL72XCommon 项目模板的新项目。 此模板包含有关消息标头 (MSH_25_GLO_DEF.xsd) 和确认 (ACK_24_GLO_DEF.xsd) 的三个公共架构和 (ACK_25_GLO_DEF.xsd)。 你必须包括这些架构在项目中因此 HL7 该 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成和/或正确验证的消息标头和确认。 此过程能够在之间通用的所有架构版本[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。  
  
 你还创建一个强大密钥、 将其分配给该程序集，然后部署程序集。 强密钥对的程序集，提供安全和标识，并且不部署所需的。 当你部署的程序集时，则将它存储在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存 (GAC) 中。  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a>若要创建项目，然后添加标头和确认架构  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。  
  
3.  在**模板**列表中，单击**BTAHL7V2XCommon 项目**。  
  
4.  在**名称**框中，键入**BTAHL7V2XCommon**作为项目名称。  
  
5.  在**位置**框中，浏览到 **\<** *驱动器***: > \Batching 教程**。  
  
6.  单击 **“确定”**。  
  
> [!NOTE]
>  在解决方案资源管理器，三个架构 （MSH_25_GLO_DEF.xsd、 ACK_24_GLO_DEF.xsd 和 ACK_25_GLO_DEF.xsd） 包含在项目中。  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a>向程序集分配强密钥和部署  
  
1.  打开**[!INCLUDE[vs2012](../../includes/vs2012-md.md)]命令提示符**。  
  
2.  上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符处，浏览到 **\<** *驱动器***>: \Batching 教程**文件夹。  
  
3.  在命令提示符处，键入**sn-k key.snk**，然后按 ENTER。 确保在输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]进行故障排除程序集。  
  
4.  在解决方案资源管理器，右键单击**BTAHL7V2Xcommon 项目**，然后单击**属性**。  
  
5.  在**BTAHL7V2XCommon 项目属性页**对话框中，单击**签名**。  
  
6.  检查**对程序集签名**复选框。  
  
7.  在**选择强名称**密钥文件下拉列表中，选择**\<浏览 … >**。  
  
8.  浏览到\<*驱动器*>: \Batching 教程中，选择**key.snk**，然后单击**打开**。  
  
9. 在 BTAHL7V2XCommon 项目属性页窗口中，单击**确定**以保存所做的更改。  
  
10. 在解决方案资源管理器，右键单击**BTAHL7V2Xcommon 项目**，然后单击**部署**。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来排查你的部署。  
  
 继续执行[步骤 2： 添加常见架构 v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)。