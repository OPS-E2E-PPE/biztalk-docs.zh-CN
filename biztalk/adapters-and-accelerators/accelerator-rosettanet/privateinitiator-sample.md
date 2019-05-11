---
title: PrivateInitiator 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27ead20d17452dcbd4982bba7f3082ee430ae6dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282571"
---
# <a name="privateinitiator-sample"></a>PrivateInitiator 示例
PrivateInitiator.odx 示例包含安装 Microsoft® BizTalk Server 的发起方专用流程的代码。 这是通用的专用流程发送和接收 RNIF 服务内容消息从默认的 SQL 适配器基于发送和接收端口。  
  
 默认情况下[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK\PrivateInitiator 中。  
  
## <a name="sample-contents"></a>示例内容  
 发起方专用流程是发起方内部的业务流程。 专用流程提供发起方公用流程和后端业务线程序之间的后端集成。 发起方专用流程与公用流程，以便启动的消息进行通信。  
  
 发起方专用流程是唯一的每个实现。 你可以为您的要求自定义 PrivateInitiator.odx 示例。 您必须小心，不产生不利影响的发起方公用流程正常运行。  
  
 有关详细信息，包括消息流的说明，请参阅[发起方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)