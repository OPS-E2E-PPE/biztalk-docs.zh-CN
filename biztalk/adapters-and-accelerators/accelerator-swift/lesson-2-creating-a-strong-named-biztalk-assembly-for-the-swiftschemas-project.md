---
title: 第 2 课：创建 swift 架构项目的强名称的 BizTalk 程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98739cfa16aa519bc67ca5a4c2b5dfa5bd2af371
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530350"
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a>第 2 课：创建 swift 架构项目的强名称的 BizTalk 程序集
在本课程中，您创建强名称对其编译并部署 BizTalk 程序集。 强名称的程序集提供了多个安全优势：  
  
- 强名称通过分配的数字签名和唯一的密钥对保证唯一性的程序集。  
  
- 强名称保护通过确保任何其他人可以生成的程序集的后续版本的程序集的沿袭。  
  
- 强名称提供可靠的完整性检查，以保证，最后一次生成之后未更改过的程序集的内容。  
  
  可以使用附带的强名称工具 (sn.exe) 来生成密钥文件[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]或[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]。  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a>若要创建的强名称的 BizTalk 程序集  
  
1. 启动 Visual Studio 命令提示符。  
  
2. 在 Visual Studio 命令提示符下，浏览到\<*驱动器*\>: \labs 文件夹。  
  
3. 在命令提示符处，键入**sn – k swift.snk**，然后按 ENTER。 确保在输出窗口中显示一条成功消息。  
  
   > [!NOTE]
   >  如果未显示正确的消息，使用 Visual Studio 来解决您的程序集。  
  
4. 在解决方案资源管理器中右键单击**swift 架构**项目，并单击**属性**。  
  
5. 在 swift 架构属性页对话框中，确保**常见属性**扩展，并选择**程序集**。  
  
6. 向下的程序集属性在右窗格中，在滚动**强名称**部分中，单击右侧的框中**程序集密钥文件**。 单击省略号按钮。  
  
7. 在程序集密钥文件对话框中，浏览到 **\<*驱动器*:\>\labs**。  
  
8. 选择**swift.snk**文件作为密钥文件，然后单击**打开**。  
  
9. 在 swift 架构属性页对话框中，单击**确定**。  
  
10. 上**文件**菜单上，单击**全部保存**以保存所做的更改。  
  
    请继续执行[第 3 课：将 SWIFT 架构添加到项目](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)。