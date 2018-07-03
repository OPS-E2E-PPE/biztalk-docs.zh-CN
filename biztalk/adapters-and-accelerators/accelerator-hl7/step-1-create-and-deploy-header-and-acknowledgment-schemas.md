---
title: 步骤 1： 创建和部署标头及确认架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50aa394f033d935c3838e056c715ee74e296b063
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989390"
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a>步骤 1： 创建和部署标头及确认架构
使用标头架构来验证消息实例的标头 （MSH 段）。 使用确认架构生成的确认消息实例。 此过程是通用于所有架构版本[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>若要创建的标头和确认架构  
  
1. 启动**Microsoft Visual Studio 2012**。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  
  
3. 在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
4. 在模板部分中，选择**BTAHL7V2XCommon 项目**，然后单击**确定**。  
  
    在解决方案资源管理器，请注意，在项目中包含三个架构 （ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd 和 MSH_25_GLO_DEF.xsd）。  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>步骤 1A： 对程序集分配强密钥并将其部署  
 使用以下过程来对程序集分配强密钥并随后部署该程序集。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>若要分配一个强密钥并将其部署该程序集  
  
1. 启动**Visual Studio 2012 命令提示符**。  
  
2. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符下，浏览到\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for HL7 \SDK\End-to-EndTutorial 文件夹。  
  
3. 在命令提示符处，键入**sn – k key.snk**，然后按 ENTER。 请确保在输出窗口中，在显示以下成功消息，然后关闭命令窗口。  
  
    **"密钥对写入到 key.snk。"**  
  
   > [!NOTE]
   >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的程序集。  
  
4. 在解决方案资源管理器中右键单击**BTAHL7V2XCommon Project1**，然后单击**属性**。  
  
5. BTAHL7V2XCommon Project1 属性页上，单击**程序集**。  
  
6. 在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 (**...**) 按钮。  
  
7. 在程序集密钥文件对话框中，浏览到\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端教程中，加速器选择**key.snk**，然后单击**打开**。  
  
8. 在 BTAHL7V2XCommon 项目属性页上，单击**确定**以保存所做的更改。  
  
9. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，请在**解决方案资源管理器**，右键单击**BTAHL7V2XCommon 项目**，然后单击**部署**。 请确保在输出窗口中将显示一条成功消息。  
  
   > [!NOTE]
   >  如果未显示正确的部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]若要排查部署问题。  
  
   请继续执行[步骤 2： 创建适用于版本 V2.3.1 的通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)。