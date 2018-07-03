---
title: 部署 A4SWIFT 信封架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae07b6b957f608e89c3ae65802d6627440201a65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004142"
---
# <a name="deploying-a4swift-envelope-schemas"></a>部署 A4SWIFT 信封架构
设置消息修复和新提交时，必须在架构项目中包括信封架构。 信封架构，如 EnvelopeMT103.xsd，需要写入 MRSR 站点。  
  
 **摘要**  
  
 将信封架构添加到你的项目，按如下所示：  
  
- 在 Visual Studio 中，为该项目包含消息架构，添加每个消息架构的信封架构。  
  
- 将对 RuntimeSchemas.dll 的引用添加到任何项目都包含一个或多个信封架构。  
  
  > [!NOTE]
  >  添加对 RuntimeSchemas.dll 的引用所需的[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]项目仅当为消息修复和新提交到项目中添加了一个信封架构时。  
  
- 将未分析消息信封架构 (EnvelopeUnparsedMessage.xsd) 添加到项目。  
  
### <a name="to-add-a-swift-envelope-schema"></a>若要添加 SWIFT 信封架构  
  
1.  在解决方案资源管理器的 Visual Studio 中，打开您的架构项目。  
  
2.  右键单击**引用**，然后单击**添加引用**。  
  
3.  在添加引用对话框中，单击**浏览**标记。  
  
4.  在选择组件对话框中，打开**查找**下拉列表。 将移动到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\Assemblies**。 选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**从列表中的程序集，并单击**添加**。  
  
5.  在中**添加引用**对话框中，单击**确定**。  
  
6.  右键单击你的项目，指向**外**，然后单击**添加现有项**。  
  
7.  在添加现有项对话框的中**查找**下拉列表框中，转到**\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Categoryn\MTxxx**。 例如，选择信封架构中， **EnvelopeMT103.xsd**，然后单击**添加**。  
  
     在添加现有项对话框的中**查找**下拉列表框中，转到。 选择的信封架构，例如，EnvelopeMT103.xsd，，然后单击添加。  
  
    > [!NOTE]
    >  A4SWIFT 添加你的项目，在信封架构，如解决方案资源管理器中所示。  
  
8.  在解决方案资源管理器中右键单击你的项目，指向**外**，然后单击**添加现有项**。  
  
9. 如果使用消息修复和新提交的功能，请在添加现有项对话框中，在**查找**下拉列表框中，转到 **\<*驱动器*\>: \Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Unparsed 消息**。 选择**EnvelopeUnparsedMessage.xsd**，然后单击**添加**。  
  
10. 在解决方案资源管理器，右键单击项目名称，然后单击**生成**。  
  
11. 在解决方案资源管理器，右键单击项目名称，然后单击**部署**。