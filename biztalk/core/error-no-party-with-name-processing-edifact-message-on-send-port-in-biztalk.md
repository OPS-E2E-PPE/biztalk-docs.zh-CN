---
title: 处理在发送端口上的 Edifact 消息时出现故障： 同名否方 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 678baacb-1f21-4081-b788-ef346c3598ca
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6becad3fefaa8167c9cf1af051731aa08be0d80a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005150"
---
# <a name="a-failure-occurred-in-processing-edifact-message-on-send-port-no-party-with-name"></a>处理在发送端口上的 Edifact 消息时出现故障： 同名否方
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|BizTalk Server EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|在发送端口 {0} 上处理 Edifact 消息时发生故障。 任何一方不存在名称 {1}。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 BizTalk 服务器无法解析为 EDIFACT 交换参与方，因为 BizTalk Server 无法与使用方与关联的发送端口交换订阅的发送端口匹配。 如果不 DestinationPartyName 属性也发件人限定符和标识符和接收方限定符和标识符属性提升，因此不可用于发送方参与方解析，将发生这种情况。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保订阅交换的发送端口和与某个参与方关联的发送端口匹配。