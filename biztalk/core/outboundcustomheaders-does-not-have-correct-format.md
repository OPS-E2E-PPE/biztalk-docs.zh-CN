---
title: OutboundCustomHeaders 不具有正确的格式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db856038267ff6c8472f85e1a9b87a389a1d8047
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393448"
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a>OutboundCustomHeaders 不具有正确的格式
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                OutboundCustomHeaders 格式不是正确的格式                |
  
## <a name="explanation"></a>解释  
 WCF 的值。InboundHeaders 或 WCF。OutboundCustomHeaders 不是采用以下格式：\<标头\>...\</headers\>。  
  
## <a name="user-action"></a>用户操作  
 包装属性值替换\<标头\>元素。  
  
 有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [通过管道组件使用 WCF 消息中的 SOAP 标头](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)