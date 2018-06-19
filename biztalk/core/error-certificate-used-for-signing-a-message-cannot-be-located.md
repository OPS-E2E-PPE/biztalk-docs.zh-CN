---
title: 用于对邮件签名的证书不能位于在本地证书存储区中 |Microsoft 文档
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
ms.openlocfilehash: d94049a0ecca4e7aec89c5163231c0b9bf4c9e3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239957"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a>无法在本地证书存储中定位用于对消息签名的证书
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|CertificateMissingError|  
|消息正文|无法在本地证书存储中定位用于对消息签名的证书。 证书指纹： {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的消息，因为标识为签名证书的证书不在所需的证书存储区中。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
1.  通过打开 BizTalk Server 管理控制台，右键单击“BizTalk 组”，然后单击“证书”节点来标识签名证书。  
  
2.  打开 MMC，添加“我的用户帐户”的管理单元，然后打开“证书”、“个人”和“证书”节点。  
  
3.  通过查找在错误消息文本中标识的指纹，确保“当前用户”证书存储区包含该签名证书的私钥。