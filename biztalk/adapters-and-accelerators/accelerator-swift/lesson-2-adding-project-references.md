---
title: "第 2 课： 添加项目引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- references [projects]
- projects, adding references
ms.assetid: ddc2bf49-cddd-4edb-8043-870897879655
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b00fc7d49024cec6f9c300444646da82069e16cc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-2-adding-project-references"></a>第 2 课： 添加项目引用
你添加项目引用，以便你管道可以访问位于 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 文件中的默认运行时架构。 此程序集文件包含与消息类型解析所需的提升属性的标头架构。  
  
 当将反汇编组件添加到接收管道供以后参考标头架构。  
  
### <a name="to-add-a-reference-to-the-default-swift-runtimeschemas-assembly"></a>若要添加到默认 SWIFT RuntimeSchemas 程序集的引用  
  
1.  在解决方案资源管理器，确保**SWIFTPipelines**展开项目。 右键单击**引用**，然后单击**添加引用**。  
  
2.  在添加引用对话框中，单击**浏览**选项卡。  
  
3.  浏览到  **\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\Assemblies * *。  
  
4.  选择**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**文件。  
  
5.  单击**添加**，然后单击**确定**。  
  
    > [!NOTE]
    >  现在选择 RuntimeSchemas 程序集 (dll) 将出现在 SWIFTPipelines 项目中的引用集合。  
  
#### <a name="to-add-a-reference-to-the-swiftpipelines-schemas-assembly"></a>若要添加对 SWIFTPipelines 架构集的引用  
  
1.  在解决方案资源管理器下**SWIFTPipelines**项目，右键单击**引用**，然后单击**添加引用**。  
  
2.  在添加引用对话框中，在**项目**选项卡上，单击**SWIFTSchemas**项目中，单击**添加**，然后单击**确定**。  
  
3.  上**文件**菜单上，单击**保存所有**以保存所做的更改。  
  
 继续执行[第 3 课： 添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。