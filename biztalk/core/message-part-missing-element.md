---
title: "消息部分缺少元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b519315f-d51d-4ca3-a0e6-d08bb920c6c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dd5a423a34d8b6ddf8f4689351b0f6dbcef53c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-part-missing-element"></a>消息部分缺少元素
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|消息部分丢失元素。 更正服务说明"{0}"消息类型"{1}"部分"{2}"，然后重新运行该向导|  
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用的服务不具有标识消息类型的元素标签。  
  
## <a name="user-action"></a>用户操作  
 将服务更正为具有正确的消息类型，然后尝试使用此服务（如果您拥有要尝试使用的 WCF 服务）。 否则，请与服务提供商联系。  
  
 有关消息的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [构造 Web 消息](../core/constructing-web-messages.md)