---
title: "部署 A4SWIFT 信封架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d47fb5f072be8969df61b0e384c700b7b0ddffb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-a4swift-envelope-schemas"></a>部署 A4SWIFT 信封架构
每当你设置消息修复和新提交时，架构项目中必须包含信封架构。 信封架构，如 EnvelopeMT103.xsd，需要将写入到 MRSR 站点。  
  
 **摘要**  
  
 向你的项目，添加信封架构，如下所示：  
  
-   在 Visual Studio 中，包含你的消息架构的项目将添加到每个消息架构信封架构。  
  
-   将对 RuntimeSchemas.dll 的引用添加到任何包含一个或多个信封架构的项目。  
  
    > [!NOTE]
    >  添加对 RuntimeSchemas.dll 的引用所需[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]项目仅在有消息修复和新提交到该项目添加信封架构时。  
  
-   将未分析消息信封架构 (EnvelopeUnparsedMessage.xsd) 添加到项目。  
  
### <a name="to-add-a-swift-envelope-schema"></a>若要添加 SWIFT 信封架构  
  
1.  在解决方案资源管理器的 Visual Studio 中，打开架构项目。  
  
2.  右键单击**引用**，然后单击**添加引用**。  
  
3.  在添加引用对话框中，单击**浏览**标记。  
  
4.  在选择组件对话框中，打开**查找**下拉列表。 将移动到 ***\<驱动器 >*: files\microsoft BizTalk Accelerator for SWIFT\<版本 > 消息 Pack\Assemblies**。 选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**从列表中的程序集，然后单击**添加**。  
  
5.  在**添加引用**对话框中，单击**确定**。  
  
6.  右键单击你的项目，指向**添加**，然后单击**添加现有项**。  
  
7.  在添加现有项对话框中，在**查找**下拉列表框中，移动到**\<驱动器 >: \program Microsoft BizTalk Accelerator for SWIFT\<版本 > 消息 Pack\SWIFT 消息\A4SWIFT-SRG\<版本 > \Categoryn\MTxxx**。 例如，选择信封架构， **EnvelopeMT103.xsd**，然后单击**添加**。  
  
     在添加现有项对话框中，在**查找**下拉列表框中，移动到。 选择信封架构，例如，EnvelopeMT103.xsd，，然后单击添加。  
  
    > [!NOTE]
    >  A4SWIFT 将添加你的项目，信封架构，如解决方案资源管理器中所示。  
  
8.  在解决方案资源管理器，右键单击你的项目，指向**添加**，然后单击**添加现有项**。  
  
9. 如果在使用添加现有项对话框中中的消息修复和新提交功能**查找**下拉列表框中，移动到  **\<*驱动器*>: \Microsoft BizTalk Accelerator for SWIFT\<版本 > 消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本 > \Unparsed 消息 * *。 选择**EnvelopeUnparsedMessage.xsd**，然后单击**添加**。  
  
10. 在解决方案资源管理器，右键单击项目名称，然后单击**生成**。  
  
11. 在解决方案资源管理器，右键单击项目名称，然后单击**部署**。