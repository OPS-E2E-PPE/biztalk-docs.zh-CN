---
title: 对 SMTP 主机属性的限制 |Microsoft Docs
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
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60eee7ce4acb940d2d0011ead80bdcf9c5ed335c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254882"
---
# <a name="restrictions-on-the-smtp-host-property"></a>对 SMTP 主机属性的限制
SMTP 主机属性是一个字符串，指定将使用 SMTP 适配器将消息从 BizTalk server 发送的 SMTP 服务器。  
  
 为此属性适用以下规则和限制：  
  
- 必须在适配器处理程序级别中，在终结点级别或这两个位置中配置此属性。  
  
- SMTP 服务器属性不能包含以下字符: ' ~ ！ @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< \> /, ?;  
  
- SMTP 服务器名称的长度不得超过 256 个字符。  
  
  SMTP 适配器始终验证 SMTP 主机名称在设计时通过使用前面所述的规则。 此外，SMTP 适配器验证 SMTP 主机名称在运行时如果通过 SMTP 适配器的动态端口发送一条消息。  
  
## <a name="see-also"></a>请参阅  
 [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)