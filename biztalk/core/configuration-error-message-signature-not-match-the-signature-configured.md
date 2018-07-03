---
title: 配置错误。 消息签名不&#39;t 与为此参与方配置的签名匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729fff283d8fa63ce9e933a0dc69a4a8f2200874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980454"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a>配置错误。 消息签名不&#39;t 与为此参与方配置的签名匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| 产品版本 |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    事件 ID     |                                                                                                     -                                                                                                      |
|  事件源   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                           |
|    组件    |                                                                                                 AS2 引擎                                                                                                 |
|  符号名称  |                                                                                                     -                                                                                                      |
|  消息正文   | 配置错误。 消息签名与为此参与方配置的签名不匹配。 请与发送合作伙伴联系，以验证使用的证书。 AS2-从:"{0}"AS2-到:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道在执行 MIME 处理时无法验证签名。 这可能是由于用于处理所接收的消息的证书不是发送方用于对消息进行签名的证书。 如果 BizTalk Server 使用错误参与方的设置来验证传入的 AS2 消息的签名，则可能会发生此错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   确保通过传入的 AS2 消息的参与方解析过程确定正确的参与方。 通过在 BizTalk Server 尝试在传入消息中的 AS2-From 标头和“参与方属性”对话框的“常规”页中“别名”列表的“EDIINT-AS2 起始”值之间查找匹配项时，验证是否解析了正确的参与方来完成该操作。 如果没有解析参与方，请在 BizTalk Server 尝试在为传入消息设置的 AS2-From 上下文属性和参与方的名称之间查找匹配项时验证是否解析了正确的参与方。  
  
-   确保在“参与方属性”对话框的“证书”页定义的证书（存储在“本地计算机\其他人”存储区中）与用于对消息进行签名的证书相符。