---
title: 第 3 课： 将 SWIFT 架构添加到项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fcaa7f9af0dd802f457f84d7661f92bcdf08157
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982038"
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a>第 3 课： 将 SWIFT 架构添加到项目
现在，有一个解决方案和新项目时，您可以将项添加到项目。 您添加的第一项是 MT103 SWIFT 付款消息的架构。 当选择架构模板时，BizTalk 编辑器中启动。  
  
### <a name="to-add-a-new-schema-to-the-project"></a>向项目添加新架构  
  
1. 在解决方案资源管理器中右键单击**swift 架构**项目，指向**添加**，然后单击**现有项**。  
  
2. 在添加现有项-swift 架构对话框中，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 架构**。  
  
3. 选择**SWIFT 基本 Types.xsd**并**SWIFT 常见数据 Types.xsd**架构，并单击**添加**。  
  
   > [!NOTE]
   >  SWIFT 基本 Types.xsd 和 SWIFT 常见数据 Types.xsd 架构显示在解决方案资源管理器 swift 架构项目下。  
  
4. 在解决方案资源管理器中右键单击**swift 架构**项目，指向**添加**，然后单击**现有项**。  
  
5. 在添加现有项-swift 架构对话框中，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103**文件夹。  
  
6. 选择**MT103.xsd**架构中，并单击**添加**。  
  
   > [!NOTE]
   >  新的架构，MT103.xsd，将显示在解决方案资源管理器下 swift 架构项目。  
  
7. 在解决方案资源管理器中双击**MT103.xsd**以便查看在 BizTalk 编辑器中的架构。  
  
   > [!NOTE]
   >  架构树 （左窗格） 和 XSD 视图 （右窗格） 显示在 BizTalk 编辑器中。  
  
8. 上**文件**菜单上，单击**全部保存**以保存所做的更改。  
  
   请继续执行[第 4 课： 生成和部署程序集](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md)。