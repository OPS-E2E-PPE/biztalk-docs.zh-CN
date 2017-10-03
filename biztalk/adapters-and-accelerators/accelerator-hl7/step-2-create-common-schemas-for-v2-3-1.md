---
title: "步骤 2： 为 V2.3.1 创建通用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, common schemas
- common schemas
ms.assetid: db1a2206-559f-475a-803d-55522cce007e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65e2860e2140a16749ad434ead77bf8a4f49eb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-common-schemas-for-v231"></a>步骤 2： 为 V2.3.1 创建通用架构
V2.3.1 架构是经常引用的架构，用于验证消息实例。  
  
### <a name="to-create-a-common-schema-for-v231"></a>若要为 V2.3.1 创建公用架构  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。  
  
2.  在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。  
  
3.  在模板部分中，选择**BTAHL7V231Common 项目**。  
  
4.  在**名称**框中，输入**BTAHL7V231Common 项目**作为项目名称。  
  
5.  在**解决方案**框中，选择**将添加到解决方案**。  
  
6.  单击 **“确定”**。  
  
    > [!NOTE]
    >  在解决方案资源管理器，三个架构 （datatypes_231.xsd、 segments_231.xsd 和 tablevalues_231.xsd） 包含在项目中。  
  
7.  在解决方案资源管理器，右键单击**BTAHL7V231Common 项目**，然后单击**属性**。  
  
8.  在 BTAHL7V231Common 属性页上，单击**签名**。  
  
9. 选择**对程序集签名**复选框。  
  
10. 在**选择强名称密钥文件**，选择**\<浏览 … >** 。  
  
11. 浏览到\<驱动器 >: \Batching 教程中，选择**key.snk**，然后单击**打开**。  
  
12. 在解决方案资源管理器，右键单击**BTAHL7V231Common 项目**，然后单击**部署**。 确保输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。  
  
 继续执行[步骤 3： 添加触发器事件 （消息） 架构](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)。