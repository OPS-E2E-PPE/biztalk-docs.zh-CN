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
ms.openlocfilehash: 6a3ba1c413d70aa37b519d3eb868f2f3692df47f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298915"
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a>用于对消息进行加密的证书已被吊销
## <a name="details"></a>详细信息  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    事件 ID     |                                            -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI  |
|    组件    |                                       AS2 引擎                                        |
|  符号名称  |                        EncryptionCertificateHasBeenRevokedError                         |
|  消息正文   | 用于对消息进行加密的证书已吊销。 证书指纹： {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道不无法处理传出消息，因为标识为加密证书的证书被吊销。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   具有消息的接收方创建一个新证书并将公钥发送给您。 将证书添加到本地计算机 \ 其他人证书存储，然后将该证书标识为发送端口属性对话框中的证书页中的加密证书。  
  
-   通过打开 BizTalk Server 管理控制台，打开为传出消息解析的参与方 AS2 属性对话框中，单击常规节点，然后清除检查证书吊销列表中禁用吊销列表检查属性。