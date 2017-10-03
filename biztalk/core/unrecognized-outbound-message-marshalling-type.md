---
title: "类型的封送处理无法识别出站消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3928bde0d81a4fe22b7c16af41c3a4b6d5c7121c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-outbound-message-marshalling-type"></a>无法识别的出站消息封送类型
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法识别的出站消息封送类型；应为 UseBodyElement 或 UseTemplate|  
  
## <a name="explanation"></a>解释  
 WCF。OutboundBodyLocation 属性设置为不同于 UseBodyElement 或 UseTemplate，自定义管道组件或业务流程中的值。  
  
## <a name="user-action"></a>用户操作  
 将 WCF.OutboundBodyLocation 属性设置为有效值。 有效值为“UseBodyElement”或“UseTemplate”。这是代码更改。   
有关出站消息的详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [配置动态发送端口使用 WCF 适配器上下文属性](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [配置 WCF 适配器](../core/configuring-the-wcf-adapters.md)