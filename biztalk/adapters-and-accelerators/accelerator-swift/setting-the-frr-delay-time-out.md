---
title: 设置 FRR 延迟超时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e141f1c2c3afff1049556c5bc041711695e9ca
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529984"
---
# <a name="setting-the-frr-delay-time-out"></a>设置 FRR 延迟超时
您必须配置 FRR 业务流程的某些时间段后，以便它不会等待 FNN 响应无限期。 如果在超时持续时间到期，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将超时消息发布到自定义超时处理程序。  
  
### <a name="to-set-the-frr-delay-time-out"></a>若要设置 FRR 延迟超时  
  
1.  单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
2.  在注册表编辑器的左窗格中，转到我的计算机/HKEY_LOCAL_MACHINE/软件/Microsoft/BizTalk Accelerator for SWIFT/FRR。  
  
    > [!IMPORTANT]
    >  将角色将添加在角色节点中定义的工作流中的位置。 若要更改该位置，您需要执行步骤 8 以更改顺序角色节点中的角色。  
  
3.  在注册表编辑器的右窗格中，双击**DelayTimeout**。  
  
4.  在中**编辑 DWORD 值**对话框中**数值数据**框中，键入超时持续时间以十六进制格式。  
  
    > [!NOTE]
    >  默认值为**FRR DelayTimeout**属性为 600 秒 （258 十六进制格式）。  
  
5.  单击“确定” 。