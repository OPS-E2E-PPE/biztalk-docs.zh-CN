---
title: 处理对帐的消息集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAA
- messages, reconciled sets
ms.assetid: 05cd0cf6-f0fd-4cbe-83c6-1ed5f2da8822
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fc9f35f9381f82df90acb92e9536bbd967901a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209037"
---
# <a name="handling-reconciled-message-sets"></a>处理已协调消息集
当 SAA 返回响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]在消息框中，记录的响应和匹配的响应或对原始消息的响应。 你可以实现自定义应用程序行为通过使用此信息。 为此，请开发自定义处理程序实现协调的消息响应集到特定于客户的反应。 你可以创建自定义处理程序执行以下操作：  
  
-   处理提供 MTS21_FIN_ACKNAK 负确认消息，指示 SWIFT 没有成功收到来自的消息的消息所具有相关的 FRR [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 这可以启用 repairer 修复消息并重新将其发送到 SAA 和 SWIFT 网络，它在修复之后希望能成功接收消息。 有关此解决方案的详细信息，请参阅[FRR 否认处理程序示例](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)。  
  
-   删除消息响应集由业务流程到文件的文件夹发布具有唯一的文件名称，该值指示集合中的消息的关系。 然后，你可以在这些消息上执行业务逻辑。  
  
-   处理超时消息。  
  
-   消息传输将结果记录，然后放弃实际的消息。