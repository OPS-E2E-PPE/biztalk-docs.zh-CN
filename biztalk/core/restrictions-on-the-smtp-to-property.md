---
title: 对 SMTP 收件人属性的限制 |Microsoft Docs
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
ms.openlocfilehash: f75539b7bcd9feb1e66695361a1a208b12eda812
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399112"
---
# <a name="restrictions-on-the-smtp-to-property"></a>对 SMTP 收件人属性的限制
**到**属性是一个字符串，指定消息的收件人的 SMTP 地址。 你可以使用 SMTP 服务器支持的分隔符列出多个地址。  
  
 有 SMTP 地址的格式的任何特定的限制。 这意味着该适配器将接受 SMTP 服务器支持的任何格式。 如果用户提供的不是有效的地址，发送操作将失败，并且 SMTP 发送适配器将报告错误。  
  
 此属性的唯一限制是它不能为空，并且其大小不能超过 256 个字符。  
  
## <a name="see-also"></a>请参阅  
 [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)