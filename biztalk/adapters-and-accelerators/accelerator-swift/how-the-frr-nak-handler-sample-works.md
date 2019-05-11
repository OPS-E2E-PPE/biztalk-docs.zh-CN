---
title: FRR NAK 处理程序示例的工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b64fb92f130defe6bd7d55ac6ccdc3b7391091
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377436"
---
# <a name="how-the-frr-nak-handler-sample-works"></a>FRR NAK 处理程序示例的工作原理
FRR NAK 自定义处理程序的示例可作为 FIN 响应对帐 (FRR) 业务流程和消息修复业务流程之间的媒介。 FRR 业务流程标识的 SWIFT 网络尝试接收消息时发生的错误。 FRR 业务流程的输出是一个错误对象的一部分消息。 FRR NAK 自定义处理程序将该消息转换成两部分消息，指示发生，启用要拾取消息修复业务流程的消息的错误的错误部分。 消息修复业务流程将打开中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体，可用于找出错误，相应地，修复消息并重新提交它，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以重新发送给 SAA。  
  
 FRR NAK 自定义处理程序处理的 SWIFT 网络无法成功接收的消息时，将执行以下步骤：  
  
1.  FRR 业务流程具有相关的失败的消息到 MTS21_FIN_ACKNAK NAK 消息后，RepairSWIFTRejectedMessage 业务流程 （自定义处理程序） 从 MessageBox 提取原始消息。 它 does 因此因为 A4SWIFT_FRRFailed 上筛选器 = = True 和 A4SWIFT_SendingServiceType ="A4SWIFT_FrrService"。  
  
2.  自定义处理程序不提取与原始消息相关的 FRR NAK MTS21_FIN_ACKNAK 消息。 相反，它创建一个错误集合对象，其中填充 BRE 验证错误，指示 A4SWIFT_FRRFailedReason 属性，并将其添加到原始消息。 消息修复业务流程可以处理这两个部分构成的消息。  
  
3.  自定义处理程序将升级以下属性以导致要拾取消息修复业务流程的消息：A4SWIFT_Failed = = True，A4SWIFT_SwiftBound = = True，和 BTS。操作 ="A4SWIFT_DASMMarkedAsFailed"。 它将部件属性数设置为 2，并设置相应的错误属性。  
  
4.  由于升级属性，而消息修复业务流程将提取该消息，并 RepairSWIFTRejectedMessage 业务流程将终止。