---
title: 禁用 BAM 跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, disabling BAM tracking
- BAM tracking
ms.assetid: ea5fef0e-7a96-46f5-81d8-9b1d8a5d24d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70760db419ac11386e0cfa83b85b89fdd0bc63f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378047"
---
# <a name="disabling-bam-tracking"></a>禁用 BAM 跟踪
默认情况下为 FIN 响应对帐启用了 BAM 跟踪。 可以禁用它，如下所示。  
  
### <a name="to-disable-bam-tracking-for-frr"></a>若要禁用 BAM 跟踪 FRR  
  
1.  单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。  
  
2.  在注册表编辑器的左窗格中，转到我的计算机/HKEY_LOCAL_MACHINE/软件/Microsoft/BizTalk Accelerator for SWIFT/FRR。  
  
    > [!IMPORTANT]
    >  FIN 响应对帐运行在每台计算机上，必须修改此注册表项。  
  
3.  在注册表编辑器的右窗格中，双击**BAMTrackingEnabled**。  
  
4.  在中**编辑 DWORD 值**对话框中**值数据**框中，键入**0**禁用 BAM 跟踪。  
  
5.  单击“确定” 。