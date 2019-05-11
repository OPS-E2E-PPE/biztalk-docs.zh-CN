---
title: 第 2 课：添加项目引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c339baa026508cc520b96480a57e55dd6c86b915
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530360"
---
# <a name="lesson-2-adding-project-references"></a>第 2 课：添加项目引用
使管道能够访问位于 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 文件中的默认运行时架构添加项目引用。 此程序集文件包含标头架构已升级的属性所需的消息类型解析。  
  
 拆装组件添加到接收管道时供以后参考标头架构。  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a>若要添加到默认 SWIFT RuntimeSchemas 程序集的引用  
  
1.  在解决方案资源管理器，请确保**SWIFTPipelines**扩展项目。 右键单击**引用**，然后单击**添加引用**。  
  
2.  在添加引用对话框中，单击**浏览**选项卡。  
  
3.  浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Assemblies**。  
  
4.  选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**文件。  
  
5.  单击**外**，然后单击**确定**。  
  
    > [!NOTE]
    >  现在选择 RuntimeSchemas 程序集 (dll) 出现在 SWIFTPipelines 项目中的引用集合中。  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a>若要添加 SWIFTPipelines 架构程序集的引用  
  
1. 在解决方案资源管理器下**SWIFTPipelines**项目，右键单击**引用**，然后单击**添加引用**。  
  
2. 在添加引用对话框中，在**项目**选项卡上，单击**swift 架构**项目，然后单击**添加**，然后单击**确定**。  
  
3. 上**文件**菜单上，单击**全部保存**以保存所做的更改。  
  
   请继续执行[第 3 课：添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。