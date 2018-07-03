---
title: 用于对消息进行加密的证书已被吊销 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4476249160f71e20012ff92f749042775132d5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971430"
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a>用于加密消息的证书已经被吊销
## <a name="details"></a>详细信息  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    事件 ID     |                                            -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI  |
|    组件    |                                       AS2 引擎                                        |
|  符号名称  |                        EncryptionCertificateHasBeenRevokedError                         |
|  消息正文   | 用于加密消息的证书已经被吊销。 证书指纹： {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的消息，因为标识为加密证书的证书已被吊销。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   让消息的接收方创建一个新证书并将公钥发送给您。 将证书添加到“本地计算机\其他人”证书存储区中，然后在“发送端口属性”对话框的“证书”页中将该证书标识为加密证书。  
  
-   通过打开 BizTalk Server 管理控制台、打开为传出消息解析的参与方的“AS2 属性”对话框，单击“常规”节点，然后清除“检查证书吊销列表”属性来禁用吊销列表检查。