---
title: 不能在本地证书存储中定位用于对消息进行签名的证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff3c7a2-954c-4c62-a7b2-06f7a38d61b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f452ff362a11a824f749fc1a9c87b0905340c467
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348965"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a>不能在本地证书存储中定位用于对消息进行签名的证书
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| 产品版本 |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    事件 ID     |                                                            -                                                             |
|  事件源   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                  |
|    组件    |                                                        AS2 引擎                                                        |
|  符号名称  |                                                 CertificateMissingError                                                  |
|  消息正文   | 不能本地证书存储中定位用于对消息进行签名的证书。 证书指纹： {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道不无法处理传出消息，因为标识为签名证书的证书不在所需的证书存储区中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
1.  通过打开 BizTalk Server 管理控制台中，右键单击 BizTalk 组，然后单击证书节点标识签名证书。  
  
2.  打开 MMC，添加管理单元为我的用户帐户，然后打开证书、 个人和证书节点。  
  
3.  请确保当前用户证书存储区通过查看错误消息文本中标识的指纹包含该签名证书的私钥。