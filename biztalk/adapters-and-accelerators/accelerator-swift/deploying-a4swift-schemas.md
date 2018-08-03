---
title: 部署 A4SWIFT 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8382141993d214ffbfc79a0a4eec3f2c06b4e456
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966358"
---
# <a name="deploying-a4swift-schemas"></a>部署 A4SWIFT 架构
您必须部署你想要交换的 SWIFT 消息的架构。  
  
 **摘要**  
  
 部署了以下架构：  
  
-   SWIFT 基 Types.xsd  
  
-   SWIFT 常见数据 Types.xsd  
  
-   对于消息类型，例如，MT103.xsd 特定的架构  
  
### <a name="to-create-a-strong-named-swift-project"></a>若要创建强名称的 SWIFT 项目  
  
1. 在 Visual Studio 中，单击**文件**，依次指向**新建**，然后单击**项目**。  
  
2. 在新建项目对话框中，在**项目类型**窗格中，选择**BizTalk 项目**文件夹。  
  
3. 在中**模板**窗格中，选择**空的 BizTalk Server 项目**。  
  
4. 在中**名称**框中，键入所需的项目名称的名称。  
  
5. 在中**解决方案**框中，选择**创建新的解决方案**。 在中**位置**框中，输入要添加到架构项目的项目的位置。  
  
6. 单击**确定**打开新项目。  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 将新项目添加到解决方案资源管理器，并指定的文件夹中创建的项目文件夹和文件。  
  
7. 启动 Visual Studio 命令提示符。  
  
8. 在 Visual Studio 命令提示符下，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT**。  
  
9. 在命令提示符处，键入**sn – k key.snk**，然后按 ENTER。 请确保在命令提示符窗口中，该值指示密钥对已写入 key.snk 显示一条消息。  
  
10. 在解决方案资源管理器，右键单击项目名称，然后依次**属性**。  
  
11. 在左窗格中**属性页**对话框中，单击**程序集**。  
  
12. 在右窗格中**属性页**对话框中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。  
  
13. 在中**程序集密钥文件**对话框中，浏览到 **\<*驱动器*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]，单击**key.snk**，然后单击**打开**。  
  
14. 在中**属性页**对话框中，单击**确定**以保存所做的更改。  
  
### <a name="to-add-a-swift-schema"></a>若要添加 SWIFT 架构  
  
1.  在解决方案资源管理器的 Visual Studio 中，打开你的项目。  
  
2.  右键单击你的项目，指向**外**，然后单击**现有项**。  
  
3.  在中**添加现有项**对话框中:\\**Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT-SRG\<版本\>\Base 架构**。 选择**SWIFT 基本 Types.xsd**并**SWIFT 常见数据 Types.xsd**架构，并单击**添加**。  
  
4.  右键单击你的项目，指向**外**，然后单击**添加现有项**。  
  
5.  在中**添加现有项**对话框中**查找**下拉列表框中，转到**\<驱动器\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category n\MTxxx**。 为选择架构的消息类型，例如**MT103.xsd**，然后单击**添加**。  
  
    > [!NOTE]
    >  A4SWIFT 添加你的项目的架构，如解决方案资源管理器中所示。  
  
6.  在解决方案资源管理器，右键单击项目名称，然后单击**生成**。  
  
7.  在解决方案资源管理器，右键单击项目名称，然后单击**部署**。