---
title: 限制到属性 SMTP |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: c876d30e-44ab-462d-8c98-64416ed6dd1f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b59495ac94b3591801101607533eb9c7dba158fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268333"
---
# <a name="restrictions-on-the-smtp-to-property"></a>到属性 SMTP 的限制
**到**属性是一个字符串，指定消息的接收方的 SMTP 地址。 可以使用 SMTP 服务器支持的分隔符列出多个地址。  
  
 对于 SMTP 地址的格式没有任何特定的限制。 这意味着适配器将接受 SMTP 服务器支持的任何格式。 如果用户提供的地址无效，则发送操作将失败，并且 SMTP 发送适配器将报告一个错误。  
  
 对于此属性的唯一限制是：此属性不能为空，并且其大小不得超过 256 个字符。  
  
## <a name="see-also"></a>另请参阅  
 [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)