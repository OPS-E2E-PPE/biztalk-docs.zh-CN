---
title: OrchestrationEventStream | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7c63610-6344-4b71-8d65-3add7883bc79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981f21440f7634fc2444f850c9b10766ae4a636b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262966"
---
# <a name="orchestrationeventstream"></a>OrchestrationEventStream
OrchestrationEventStream (OES) API 用于应用程序运行在安装有 BizTalk Server 的计算机上，且您正在跟踪属于 BizTalk 业务流程事务的项的情况下。  
  
 OES API 最初将跟踪数据存储到 BizTalk MessageBox 数据库中。 跟踪数据解码服务 (TDDS) 会定期处理这些数据，并将其持久化到 BAM 主导入数据库。  
  
 OES API 位于 Microsoft.BizTalk.Bam.EventObservation 命名空间。 若要使用该 API，必须将 Microsoft.Biztalk.BAM.Xlangs.dll 添加到项目中。  
  
## <a name="oes-members"></a>OES 成员  
 OES API 派生自 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) 类。  
  
 OES 实现了 EventStream 类中的所有方法，但有以下例外情况：  
  
 **public static void Clear();**  
  
 无操作。  
  
 **public static void Flush();**  
  
 无操作。  
  
## <a name="see-also"></a>请参阅  
 [EventStream 类](../core/eventstream-classes.md)