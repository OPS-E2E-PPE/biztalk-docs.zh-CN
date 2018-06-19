---
title: 出现故障。 处理 X12 发送端口上的消息： 具有名称的否方 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af059a04-3b7c-48e2-a3bf-48ad62deb139
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e620797d45fb0b3d2ef929865a4b8bb98d2d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225349"
---
# <a name="a-failure-occurred-in-processing-x12-message-on-send-port-no-party-with-name"></a>出现故障。 处理 X12 发送端口上的消息： 具有名称的否方
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|在发送端口 {0} 上处理 X12 消息时发生故障。 任何一方不存在名称 {1}。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表示 BizTalk Server 无法解析 x12 参与方交换因为 BizTalk Server 无法与使用方与关联的发送端口交换订阅的发送端口匹配。 如果不 DestinationPartyName 属性，也不发件人限定符、 发件人标识符、 接收方限定符，而且接收方标识符属性提升，因此不可用于发送方参与方解析，将发生这种情况。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，确保交换订阅发送端口与匹配与方关联的发送端口。