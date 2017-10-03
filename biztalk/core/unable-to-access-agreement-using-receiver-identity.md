---
title: "无法使用接收方标识的访问协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41b126ca0ebb96716f21381d2e1681ea59bd414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a>无法使用接收方身份访问协议
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|UnableToLocateAS2PartyByPartyNameError|  
|消息正文|无法使用接收方标识的访问协议： {0}|  
  
## <a name="explanation"></a>解释  
 此错误表明发送管道无法确定传出的 AS2 消息的参与方，因为它无法匹配传出消息的 AS2To 上下文属性或 Http.UserHttpHeaders 上下文属性中的 AS2To 属性和“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 属性中参与方的名称。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 属性设置为与出错的 AS2 消息关联的相应参与方名称。