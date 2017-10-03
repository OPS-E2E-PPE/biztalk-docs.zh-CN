---
title: "SMTP 主机属性的限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], restrictions
- SMTP adapters, restrictions
ms.assetid: 6dbdb6dc-0062-4444-a4c8-6e2a7900f533
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42173fa0ccb01b3ced42965af74e1fcc01d12aba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="restrictions-on-the-smtp-host-property"></a>SMTP 主机属性的限制
SMTP 主机属性是一个字符串，它指定 SMTP 适配器将用于从 BizTalk 服务器发送消息的 SMTP 服务器。  
  
 此属性适用以下规则和限制：  
  
-   必须在适配器处理程序级别、终结点级别或同时在这两个级别上配置此属性。  
  
-   SMTP 服务器属性不能包含以下字符: ' ~ ！ @ # $ ^ & * ( ) = + [ ] { } \ &#124; ; : ' " , \< > /, ?;  
  
-   SMTP 服务器名称的长度不得超过 256 个字符。  
  
 SMTP 适配器将始终在设计时通过使用上述规则验证 SMTP 主机名称。 此外，如果 SMTP 适配器通过动态端口发送消息，则它将在运行时验证 SMTP 主机名称。  
  
## <a name="see-also"></a>另请参阅  
 [配置 SMTP 适配器时的限制](../core/restrictions-when-configuring-the-smtp-adapter.md)