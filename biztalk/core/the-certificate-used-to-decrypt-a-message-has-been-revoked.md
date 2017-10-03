---
title: "用于解密消息的证书已被吊销 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01767cb2-b16e-4b4b-ac4d-cd79b6c8860a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cd9404f13f737b4cb82317193344e006979d333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a>用于解密消息的证书已经被吊销
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|DecryptionCertificateHasBeenRevokedError|  
|消息正文|用于解密消息的证书已经被吊销。 证书指纹： {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的消息，因为用于解密消息的证书已被吊销。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   创建新的证书来替换被吊销的证书。 将该证书添加到“当前用户/个人”证书存储区中，然后发送用于发送 AS2 消息的证书的公钥。  
  
-   通过打开 BizTalk Server 管理控制台、打开为传出消息解析的参与方的“AS2 属性”对话框，单击“常规”节点，然后清除“检查证书吊销列表”属性来禁用吊销列表检查。