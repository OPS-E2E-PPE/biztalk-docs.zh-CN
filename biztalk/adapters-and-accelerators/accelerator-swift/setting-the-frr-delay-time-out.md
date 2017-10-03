---
title: "设置 FRR 延迟超时 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbf4c08984876627c0f11f935b0be3e32769b5f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-frr-delay-time-out"></a>设置 FRR 延迟超时
您必须配置 FRR 业务流程超时后某些持续时间，以便它将不 FNN 响应无限期等待。 如果在超时持续时间到期，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将超时消息发布到自定义超时处理程序。  
  
### <a name="to-set-the-frr-delay-time-out"></a>若要设置 FRR 延迟超时时间  
  
1.  单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
2.  在注册表编辑器的左窗格中，移动到我的计算机/HKEY_LOCAL_MACHINE/软件/Microsoft/BizTalk Accelerator for SWIFT/FRR。  
  
    > [!IMPORTANT]
    >  将在角色节点中定义的工作流中的位置添加角色。 若要更改该位置，你需要执行步骤 8 以更改角色节点中的角色的顺序。  
  
3.  在注册表编辑器的右窗格中，双击**DelayTimeout**。  
  
4.  在**编辑 DWORD 值**对话框中，在**值数据**框中，键入超时持续时间以十六进制格式。  
  
    > [!NOTE]
    >  默认值为**FRR DelayTimeout**属性为 600 秒 （258 十六进制）。  
  
5.  单击 **“确定”**。