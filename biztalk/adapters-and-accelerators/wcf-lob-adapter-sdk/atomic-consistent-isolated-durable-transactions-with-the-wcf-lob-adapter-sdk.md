---
title: 配置使用 WCF LOB 适配器 SDK 原子、 一致、 隔离和持久的事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c20d2613-c77d-4b0d-b2e2-3ed28a8fb36c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37b39ec0e240a2d4ee9ba1239cf27d7b118ca0ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007702"
---
# <a name="configure-atomic-consistent-isolated-and-durable-transactions-using-the-wcf-lob-adapter-sdk"></a>配置使用 WCF LOB 适配器 SDK 原子、 一致、 隔离和持久的事务
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]支持通过公开的功能所依赖的事务[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。 通过使用公开的 API [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，您的适配器可以支持事务和程序的操作：  
  
- **原子**，确保的所有挂起的更新都已提交或 none 提交和回滚到其以前的状态。  
  
- **一致**，确保所做的更改从一个一致的状态到另一个。  
  
- **独立**，阻止访问未提交的更改，在其他挂起的事务的事务。  
  
- **持久**，这意味着提交后，更新将为持久遇到故障时。  
  
  适配器开发人员针对关系数据库系统或其他业务线系统的支持 （或预期） 的事务将需要确定如何在目标系统支持，并公开的事务支持，然后确定相应[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]要使用的事务模型。  
  
  有关详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]事务，请参阅[Windows Communication Foundation 事务概述](https://msdn.microsoft.com/library/ms733904.aspx)。 
  
## <a name="see-also"></a>请参阅  
 [规划和设计您的适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)