---
title: PrivateResponder 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a02d4b2d902f2dad24a20c150e474e671f582a66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282519"
---
# <a name="privateresponder-sample"></a>PrivateResponder 示例
PrivateResponder.odx 示例包含用于安装 Microsoft® 的响应方专用流程的代码[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 此通用专用流程将发送和接收 RNIF 服务内容消息从默认的 SQL 适配器基于发送和接收端口。  
  
 默认情况下[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*>: \Program Files\\Microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\PrivateResponder。  
  
## <a name="sample-contents"></a>示例内容  
 响应方专用流程是响应方内部的业务流程。 专用流程提供响应方公用流程和后端业务线程序之间的后端集成。 响应方专用流程与公用流程，以便响应消息进行通信。  
  
 响应方专用流程是唯一的每个实现。 你可以为您的要求自定义 PrivateResponder.odx 示例。 您必须小心，不产生不利影响响应方公用流程的正常运行。  
  
 有关详细信息，包括消息流的说明，请参阅[响应方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)