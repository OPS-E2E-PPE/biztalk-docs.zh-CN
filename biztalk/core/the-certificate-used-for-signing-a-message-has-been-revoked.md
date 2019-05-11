---
title: 用于对消息进行签名的证书已被吊销 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f822235a-8ad8-4b63-94de-9b7f9361a071
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9a122f5b8d340ba1bed2dca5062edabf2d46e84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298914"
---
# <a name="the-certificate-used-for-signing-a-message-has-been-revoked"></a>用于对消息进行签名的证书已被吊销
## <a name="details"></a>详细信息  
  
|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  产品名称   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 产品版本 |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    事件 ID     |                                            -                                             |
|  事件源   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI  |
|    组件    |                                        AS2 引擎                                        |
|  符号名称  |                          SigningCertificateHasBeenRevokedError                           |
|  消息正文   | 用于对消息进行签名的证书已吊销。 证书指纹： {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明，发送管道无法处理传出消息因为标识为签名证书的证书已被吊销。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   创建新的证书替换已吊销的证书。 将证书添加到当前用户证书存储标识为签名证书中的组属性对话框中，证书页，然后将该证书的公钥发送到的 AS2 消息接收方。  
  
-   通过打开 BizTalk Server 管理控制台，打开为传出消息解析的参与方 AS2 属性对话框中，单击常规节点，然后清除检查证书吊销列表中禁用吊销列表检查属性。