---
title: "步骤 1： 创建和部署常见标头和确认架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a134071ee1973961e0fb4ed9b4da73ad87d8dbb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a>步骤 1： 创建和部署常见标头和确认架构
使用标头架构来验证消息实例的标头 （MSH 段）。 确认架构用于生成消息实例确认。 跨所有 HL7 架构版本，此过程是公共的。  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>若要创建的标头和确认的架构  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
3.  在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
4.  在**模板**列表中，选择**BTAHL7V2XCommon 项目**。  
  
5.  在**名称**字段中，键入**Interrogative_2XSchemas**，然后单击**确定**。  
  
     在解决方案资源管理器，请注意，在项目中包含三个架构 （ACK_24_GLO_DEF.xsd、 ACK_25_GLO_DEF.xsd 和 MSH_25_GLO_DEF.xsd）。  
  
     使 Visual Studio 保持打开状态。  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>步骤 1A： 向程序集分配强密钥和部署  
 使用以下过程向程序集分配强密钥，然后将部署程序集。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>分配一个强密钥和部署程序集  
  
1.  启动**Visual Studio 2012 的命令提示符**。  
  
2.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]命令提示符下，你将目录更改为\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\Interrogative 教程文件夹。  
  
3.  在命令提示符处，键入**sn-k key.snk**，然后按**Enter**。 确保在输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]进行故障排除程序集。  
  
4.  在解决方案资源管理器，右键单击**Interrogative_2XSchemas**项目，，然后单击**属性**。  
  
5.  在 Interrogative_2XSchemas 属性页对话框中，单击**程序集**。  
  
6.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
7.  在程序集密钥文件对话框中，浏览到\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\Interrogative 教程中，单击**key.snk**，然后单击**打开**。  
  
8.  在 Interrogative_2XSchemas 属性页对话框中，单击**确定**以保存所做的更改。  
  
9. 在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，右键单击**Interrogative_2XSchemas**项目，，然后单击**部署**。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来排查你的部署。  
  
 继续执行[步骤 2： 为 V2.4 创建通用架构](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)。