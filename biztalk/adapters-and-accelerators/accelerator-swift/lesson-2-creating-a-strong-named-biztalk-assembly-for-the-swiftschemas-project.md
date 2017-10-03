---
title: "第 2 课： 创建 SWIFTSchemas 项目的具有强名称 BizTalk 程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28afb0b029924a49dfd9a1bff87c5c847157d669
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a>第 2 课： 创建 SWIFTSchemas 项目的具有强名称 BizTalk 程序集
在本课程中，你可以创建强名称对其编译并部署 BizTalk 程序集。 具有强名称程序集提供多种安全优势：  
  
-   强名称保证通过将数字签名和唯一的密钥对分配的程序集的唯一性。  
  
-   强名称可避免通过确保没有其他任何人可以生成程序集的后续版本的程序集的沿袭。  
  
-   强名称提供可靠的完整性检查以确保自上次生成以来尚未更改的程序集的内容。  
  
 你可以使用附带的强名称工具 (sn.exe) 生成的密钥文件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]或[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]。  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a>若要创建具有强名称的 BizTalk 程序集  
  
1.  启动 Visual Studio 命令提示符。  
  
2.  在 Visual Studio 命令提示符处，浏览到\<*驱动器*>: \labs 文件夹。  
  
3.  在命令提示符处，键入**sn-k swift.snk**，然后按 ENTER。 确保在输出窗口中显示一条成功消息。  
  
    > [!NOTE]
    >  如果未显示正确的消息，请使用 Visual Studio 进行故障排除程序集。  
  
4.  在解决方案资源管理器，右键单击**SWIFTSchemas**项目，，然后单击**属性**。  
  
5.  在 SWIFTSchemas 属性页对话框中，确保**通用属性**是展开，然后选择**程序集**。  
  
6.  向下右窗格中，在和中的程序集属性滚动**强名称**部分中，单击右侧的框中**程序集密钥文件**。 单击省略号按钮。  
  
7.  在程序集密钥文件对话框中，浏览到  **\<*驱动器*: > \labs**。  
  
8.  选择**swift.snk**文件作为的密钥文件，然后单击**打开**。  
  
9. 在 SWIFTSchemas 属性页对话框中，单击**确定**。  
  
10. 上**文件**菜单上，单击**保存所有**以保存所做的更改。  
  
 继续执行[第 3 课： 向项目中添加 SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)。