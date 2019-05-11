---
title: 无效的客户端证书指纹 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f349dbc2eb3ffd6a1bfa38c3231461d45a8ae7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381387"
---
# <a name="invalid-client-certificate-thumbprint"></a>客户端证书指纹无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |       客户端证书指纹无效;预期的 40 个十六进制数字。       |
  
## <a name="explanation"></a>解释  
 指定了无效的客户端证书指纹。  
  
## <a name="user-action"></a>用户操作  
 在代码中配置 WCF 发送端口，客户端证书属性的用户界面需要十六进制 40 位值。 例如：798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 证书的其他信息，请参阅：  
  
-   [安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)