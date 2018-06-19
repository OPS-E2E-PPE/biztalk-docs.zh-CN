---
title: 第 2 课： 确认部署使用业务规则 Composer 工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, verifying
- verifying, business rules
- verifying, Business Rule Composer tool
- business rules, Business Rule Composer tool
- Business Rule Composer tool
ms.assetid: 337dc469-cf9e-406b-90ae-0f580b17d7c9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3115dc425fedca9019f0e5e5171f7234e6fbdbb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210237"
---
# <a name="lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool"></a>第 2 课： 确认使用业务规则 Composer 工具部署
在本课程中，你可以确认业务规则编辑器工具创建你的词汇和部署你的策略。 词汇是在规则组合中使用的词汇元素的集合。 策略是版本控制的业务规则集合。  
  
### <a name="to-confirm-the-deployment-using-the-business-rule-composer-tool"></a>若要确认使用业务规则编辑器工具部署  
  
1.  启动**业务规则编辑器**BizTalk Server 中。  
  
2.  在打开规则存储对话框中，单击**确定**。  
  
3.  安装完成后，在业务规则编辑器工具的事实数据资源管理器窗格中下, 图中所示确认在事实数据资源管理器，显示所需的词汇。  
  
     ![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")  
  
4.  在策略资源管理器，确认业务规则编辑器工具部署以下策略：  
  
     MT103_Master_Policy  
  
     MT103_Validation_Policy  
  
     SWIFT_NetworkRule149_Policy  
  
     SWIFT_NetworkRule150_Policy  
  
     SWIFT_NetworkRule151_Policy  
  
     SWIFT_NetworkRule175_Policy  
  
     SWIFT_NetworkRule2_Policy  
  
     SWIFT_NetworkRule201_Policy  
  
     SWIFT_NetworkRule202_Policy  
  
     SWIFT_NetworkRule203_Policy  
  
     SWIFT_NetworkRule204_Policy  
  
     SWIFT_NetworkRule205_Policy  
  
     SWIFT_NetworkRule206_Policy  
  
     SWIFT_NetworkRule207_Policy  
  
     SWIFT_NetworkRule209_Policy  
  
     SWIFT_NetworkRule210_Policy  
  
     SWIFT_NetworkRule212_Policy  
  
     SWIFT_NetworkRule213_Policy  
  
     SWIFT_NetworkRule215_Policy  
  
     SWIFT_NetworkRule216_Policy  
  
     SWIFT_NetworkRule217_Policy  
  
     SWIFT_NetworkRule218_Policy  
  
     SWIFT_NetworkRule244_Policy  
  
     SWIFT_NetworkRule245_Policy  
  
     SWIFT_NetworkRule81_Policy  
  
     SWIFT_PartyIdentifier_Policy  
  
     SWIFT_Reference_Policy  
  
### <a name="to-view-a-policy"></a>若要查看策略  
  
1.  在业务规则编辑器的策略资源管理器窗格中，确保**SWIFT_NetworkRule149_Policy**展开，，然后展开**版本 1.0 – 部署**节点。  
  
2.  双击**Validate_MT103**节点将其打开。  
  
     策略将在屏幕右侧的编辑器窗格中打开。  
  
 继续执行[模块 7： 测试的有效的平面文件实例](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)。