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
ms.openlocfilehash: 630ce4850c2bb11f9b5a18db03204ef2c1e24cae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003726"
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
 此错误表明发送管道无法确定传出的 AS2 消息的参与方，因为它无法匹配传出消息的 AS2To 上下文属性或 Http.UserHttpHeaders 上下文属性中的 AS2To 属性和“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 属性中参与方的名称。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将“AS2 属性”对话框的“作为 AS2 消息接收方的参与方”页中的 AS2-To 属性设置为与出错的 AS2 消息关联的相应参与方名称。