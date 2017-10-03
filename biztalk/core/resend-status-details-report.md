---
title: "重新发送状态详细信息报表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbc9d44-9a9a-4272-a138-ebd126a9f809
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2335b10da205258f32a6676a6fee2a3ff32fef65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="resend-status-details-report"></a>重新发送状态详细信息报告
将参与方的“作为 AS2 接收方的参与方”属性配置为在未收到 MDN 情况下重新发送 AS2 消息时，此状态报告显示有关所做的重试信息。  
  
 此报表显示通过一条消息在 AS2/MDN 状态报表中，右键单击，然后单击**查看可靠消息传递状态**。 随后，“重新发送状态详细信息”页将显示对此消息所做的重新发送尝试的相关信息。  
  
 此报表才可用，如果选择了**重新发送 AS2 消息如果未收到 MDN**方作为相关方的 AS2 消息接收方属性中。  
  
 此报告显示在以下各页中对消息所做的重新尝试的相关信息：  
  
|第|显示的数据|  
|----------|--------------------|  
|**常规**|当前发送尝试和重新发送配置的索引。|  
|**重新发送历史记录**|消息发送尝试的历史记录。|