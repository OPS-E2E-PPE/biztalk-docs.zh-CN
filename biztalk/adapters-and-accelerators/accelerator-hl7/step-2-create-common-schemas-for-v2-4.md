---
title: "步骤 2： 为 V2.4 创建通用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07260c5f0d161698545ff7fd5b5177a5374f3d04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-common-schemas-for-v24"></a>步骤 2： 为 V2.4 创建通用架构
V2.4 架构是经常引用的架构，用于验证查询和响应消息实例。  
  
### <a name="to-create-the-common-schemas-for-v24"></a>若要为 V2.4 创建通用架构  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
3.  在**模板**列表中，选择**BTAHL7V24Common 项目**。  
  
4.  在**名称**字段中，键入**Interrogative_24Schemas**。  
  
5.  在解决方案字段中，选择**将添加到解决方案**，然后单击**确定**。  
  
     在解决方案资源管理器，请注意，在项目中包含三个架构 （datatypes_24.xsd、 segments_24.xsd 和 tablevalues_24.xsd）。  
  
6.  在解决方案资源管理器，右键单击**Interrogative_24Schemas**项目，，然后单击**属性**。  
  
7.  在 Interrogative_24Schemas 属性页对话框中，单击**程序集**。  
  
8.  在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
9. 在**程序集密钥文件**对话框中，浏览到\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\Interrogative 教程中，单击**key.snk**，然后单击**打开**。  
  
10. 在 Interrogative_24Schemas 属性页对话框中，单击**确定**以保存所做的更改。  
  
11. 在解决方案资源管理器，右键单击**Interrogative_24Schemas**项目，，然后单击**部署**。 单击**确定**到对话框，询问你要将更改保存到解决方案。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。  
  
 继续执行[步骤 3： 创建和部署的触发器事件 （消息） 项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)。