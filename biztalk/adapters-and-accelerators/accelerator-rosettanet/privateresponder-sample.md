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
ms.openlocfilehash: f2e44157c1b7a4e545bad23c5d9b6dcd9fa87cfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986862"
---
# <a name="privateresponder-sample"></a>PrivateResponder 示例
PrivateResponder.odx 示例包含用于安装 Microsoft® 的响应方专用流程的代码[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 此通用专用流程从基于默认 SQL 适配器的发送和接收端口发送和接收 RNIF 服务内容消息。  
  
 默认情况下[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装中的示例\<*驱动器*>: \Program Files\\Microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\PrivateResponder。  
  
## <a name="sample-contents"></a>示例内容  
 响应方专用流程是响应方内部的业务流程。 该专用流程提供响应方公用流程和后端业务线程序之间的后端集成。 响应方专用流程与公用流程进行通信以响应消息。  
  
 每个实现的响应方专用流程都是唯一的。 可以根据所需自定义 PrivateResponder.odx 示例。 你必须小心，确保不会对响应方公用流程的正常运行产生不利影响。  
  
 有关详细信息，包括消息流的说明，请参阅[响应方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)