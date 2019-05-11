---
title: 无法使用接收方身份访问协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbdd869e244f3d59ebd267d492112a1e29441c2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258498"
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a>无法使用接收方身份访问协议
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                         UnableToLocateAS2PartyByPartyNameError                         |
|  消息正文   |                无法使用接收方身份访问协议： {0}                 |
  
## <a name="explanation"></a>解释  
 此错误表明发送管道无法因为它无法匹配的出站消息的 AS2To 上下文属性或 Http.UserHttpHeaders 上下文属性的名称中的 AS2To 属性确定传出的 AS2 消息的参与方在 AS2 参与方的中作为 AS2 消息接收方的 AS2 属性对话框的页的参与方属性。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，将 AS2-到中作为 AS2 消息接收方到相应的参与方名称与处于错误的 AS2 消息相关联的 AS2 属性对话框页的参与方属性。