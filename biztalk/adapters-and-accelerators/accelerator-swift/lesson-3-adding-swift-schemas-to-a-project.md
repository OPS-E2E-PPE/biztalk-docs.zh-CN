---
title: 第 3 课： 将 SWIFT 架构添加到项目 |Microsoft 文档
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
ms.openlocfilehash: 12fb5741b75fb9792cbabf46bf7a0402972d7bb4
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961987"
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a>第 3 课： 将 SWIFT 架构添加到项目
现在，你有一个解决方案和一个新的项目，你可以向项目添加项。 你添加的第一项是 MT103 SWIFT 付款的消息架构。 当你选择架构模板时，将启动 BizTalk 编辑器。  
  
### <a name="to-add-a-new-schema-to-the-project"></a>向项目添加新架构  
  
1.  在解决方案资源管理器，右键单击**SWIFTSchemas**项目，指向**添加**，然后单击**现有项**。  
  
2.  在添加现有项-SWIFTSchemas 对话框中，浏览到 **\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 架构**。  
  
3.  选择**SWIFT 基 Types.xsd**和**SWIFT 常见数据 Types.xsd**架构，，然后单击**添加**。  
  
    > [!NOTE]
    >  SWIFT 基 Types.xsd 和 SWIFT 常见数据 Types.xsd 架构显示在解决方案资源管理器 SWIFTSchemas 项目下。  
  
4.  在解决方案资源管理器，右键单击**SWIFTSchemas**项目，指向**添加**，然后单击**现有项**。  
  
5.  在添加现有项-SWIFTSchemas 对话框中，浏览到 **\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103**文件夹。  
  
6.  选择**MT103.xsd**架构，，然后单击**添加**。  
  
    > [!NOTE]
    >  新架构，MT103.xsd，将显示在解决方案资源管理器 SWIFTSchemas 项目下。  
  
7.  在解决方案资源管理器中，双击**MT103.xsd**若要查看 BizTalk 编辑器中的架构。  
  
    > [!NOTE]
    >  架构树 （左窗格中） 和 XSD 视图 （右窗格） 将出现在 BizTalk 编辑器中。  
  
8.  上**文件**菜单上，单击**保存所有**以保存所做的更改。  
  
 继续执行[第 4 课： 构建和部署程序集](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md)。