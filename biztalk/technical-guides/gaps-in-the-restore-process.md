---
title: 在还原过程中的缺口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 616c4f36-8ed6-4b99-b97a-5635627dfc17
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b7d3ccadd950f5a955430b982c1a6f79a262864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298093"
---
# <a name="gaps-in-the-restore-process"></a>在还原过程中的缺口
时查看 Master.dbo.bts_LogShippingHistory 表中的记录，你可能会观察还原集方面的差距。 这可能由多种原因引起。 但是，即使发生缺口，则可以还原的目标系统的稳定性。 间隔必须跟设置为修复目标环境的完整备份还原。 如果间隔后面不是完整备份集还原，目标环境不稳定且不能还原处于一致状态。  
  
> [!NOTE]  
>  仅在重新创建数据库以及修复日志历史记录备份链中的问题时，才需要还原完整备份。 只要还原时，问题不会发生，将不还原完整备份集，因为它们在日志备份链未参与。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除日志传送](../technical-guides/troubleshooting-log-shipping.md)