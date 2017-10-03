---
title: "无法序列化批处理消息，因为没有任何与关联一方发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d697ff9c-a6d1-4a3c-9ec3-4cd496f7eec2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b20d10a2c7b584eccc7d1fb57e5132a4ac0d608
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batch-message-cannot-be-serialized-as-there-is-no-party-associated-with-send-port"></a>批消息不能序列化，因为没有与发送端口相关联的参与方
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|BatchMessageSerializationFailureDueToMissingParty|  
|消息正文|批处理消息无法序列化，因为没有与发送端口 {0} 关联的参与方。 请确保有参与方与该端口关联。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理保留的交换，因为它无法确定应将消息发送到的参与方。 它无法确定参与方，因为未设置 DestinationPartyName 上下文属性。 因此，发送管道无法确定信封设置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请通过直通发送管道传递消息，然后确定该消息的 DestinationPartyName 上下文属性。 验证参与方是否存在。 如果不存在，请创建参与方，然后重新发送消息。