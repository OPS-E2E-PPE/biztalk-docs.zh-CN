---
title: 步骤 1： 添加标头及确认架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0712e2ee4498b8f6f2eb8cb9527aa8ee8e4582
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011296"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a>步骤 1： 添加标头及确认架构
在此步骤中，你创建基于 BTAHL72XCommon 项目模板的新项目。 此模板包含消息标头 (MSH_25_GLO_DEF.xsd) 和确认 (ACK_24_GLO_DEF.xsd) 的三个常见架构和 (ACK_25_GLO_DEF.xsd)。 您必须包括这些架构在项目中因此该 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 生成和/或正确验证消息标头和确认。 此过程是通用于所有架构版本[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。  
  
 你还创建强密钥，将其分配给该程序集，并随后部署该程序集。 强密钥提供安全和标识了程序集，并且部署所需的。 在部署程序集时，它存储在配置数据库 （也称为 BizTalk 管理数据库） 和全局程序集缓存 (GAC) 中。  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a>若要创建项目并添加标头和确认架构  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  
  
2. 在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。  
  
3. 在中**模板**列表中，单击**BTAHL7V2XCommon 项目**。  
  
4. 在中**名称**框中，键入**BTAHL7V2XCommon**作为项目名称。  
  
5. 在中**位置**框中，浏览到**\<**<em>驱动器</em>**:\>\Batching 教程**。  
  
6. 单击“确定” 。  
  
> [!NOTE]
>  在解决方案资源管理器，在项目中包括三个架构 （MSH_25_GLO_DEF.xsd、 ACK_24_GLO_DEF.xsd 和 ACK_25_GLO_DEF.xsd）。  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a>若要对程序集分配强密钥并将其部署  
  
1. 打开**Visual Studio 命令提示符**。  
  
2. 上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符下，浏览到**\<**<em>驱动器</em>**\>: \Batching 教程**文件夹。  
  
3. 在命令提示符处，键入**sn – k key.snk**，然后按 ENTER。 确保在输出窗口中显示一条成功消息。  
  
   > [!NOTE]
   >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的程序集。  
  
4. 在解决方案资源管理器中右键单击**BTAHL7V2Xcommon 项目**，然后单击**属性**。  
  
5. 在中**BTAHL7V2XCommon 项目属性页**对话框中，单击**签名**。  
  
6. 检查**为程序集签名**复选框。  
  
7. 在中**选择强名称**密钥文件下拉列表中，选择**\<浏览...\>**.  
  
8. 浏览到\<*驱动器*\>: \Batching 教程中，选择**key.snk**，然后单击**打开**。  
  
9. 在 BTAHL7V2XCommon 项目属性页窗口中，单击**确定**以保存所做的更改。  
  
10. 在解决方案资源管理器中右键单击**BTAHL7V2Xcommon 项目**，然后单击**部署**。 请确保在输出窗口中将显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]若要排查部署问题。  
  
    请继续执行[步骤 2： 添加适用于 v2.3.1 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)。