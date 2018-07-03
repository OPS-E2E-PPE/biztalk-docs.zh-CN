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
ms.openlocfilehash: 74551ac825f9e517bec1d07edc7f288db732b348
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018879"
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
|  消息正文   |       客户端证书指纹无效；应为十六进制的 40 位数字。       |
  
## <a name="explanation"></a>解释  
 指定的客户端证书指纹无效。  
  
## <a name="user-action"></a>用户操作  
 在用于配置 WCF 发送端口的代码中，用户界面的客户端证书属性应为十六进制的 40 位值。 示例： 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 有关证书的其他信息，请参阅以下内容：  
  
-   [安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)