---
title: "PrivateInitiator 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 853b77e24359d6a833d526fc07166384ea946887
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="privateinitiator-sample"></a>PrivateInitiator 示例
PrivateInitiator.odx 示例包含通过安装发起程序专用进程的代码[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server。 此通用专用流程从基于默认的 SQL 适配器的发送和接收端口发送和接收 RNIF 服务内容消息。  
  
 默认情况下，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet\SDK\PrivateInitiator 快捷键。  
  
## <a name="sample-contents"></a>示例内容  
 发起方专用流程是发起方内部的业务流程。 该专用流程提供发起方公用流程和后端业务线程序之间的后端集成。 发起方专用流程与公用流程进行通信以发起消息。  
  
 每个实现的发起方专用流程都是唯一的。 可以根据所需自定义 PrivateInitiator.odx 示例。 你必须小心，确保不会对发起方公用流程的正常运行产生不利影响。  
  
 有关详细信息，包括消息流的说明，请参阅[发起方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)