---
title: "OutboundCustomHeaders 没有正确的格式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b81a8c9c605f646a8ac0b6df2045af05eb58e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a>OutboundCustomHeaders 没有正确的格式
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|OutboundCustomHeaders 的格式不正确|  
  
## <a name="explanation"></a>解释  
 WCF 的值。InboundHeaders 或 WCF。OutboundCustomHeaders 不是以下格式：\<标头 >...\</headers >。  
  
## <a name="user-action"></a>用户操作  
 包装属性值，值\<标头 > 元素。  
  
 有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [在与管道组件的 WCF 消息中使用 SOAP 标头](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)