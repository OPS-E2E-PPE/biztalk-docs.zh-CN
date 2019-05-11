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
ms.openlocfilehash: b78dc27ff21787c6b57e65a2cadb7564e080c1a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391556"
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
|  消息正文   | 配置错误。 消息签名与为此参与方配置的签名不匹配。 与发送合作伙伴联系，并验证使用的证书。 AS2-From:"{0}" AS2-To:"{1}" MessageID:"{2}" |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 接收管道无法验证签名，在执行 MIME 处理时。 这可能会导致从使用不同的证书来处理不用于对消息进行签名是发送方接收的消息。 如果 BizTalk Server 使用错误参与方的设置来验证传入的 AS2 消息的签名，这可能发生。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   请确保正确的参与方由传入的 AS2 消息的参与方解析过程。 通过验证正确的参与方解析时 BizTalk Server 尝试查找匹配项的 as2-From 标头中的传入消息和参与方属性对话框中的常规页中的别名列表中的 EDIINT-AS2 起始值。 如果没有解析参与方，验证是否正确的参与方解决在 BizTalk Server 尝试查找匹配 AS2-From 上下文属性设置为传入消息和参与方的名称。  
  
-   请确保参与方属性对话框中，在证书页中定义并存储在本地计算机 \ 其他人的存储区中的证书对应于用于对消息进行签名的证书。