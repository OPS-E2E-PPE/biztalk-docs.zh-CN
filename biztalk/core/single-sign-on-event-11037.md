---
title: 单一登录： 事件 11037 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceec837a53d4cad3c236373a907497795efbd12a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998894"
---
# <a name="single-sign-on-event-11037"></a>单一登录： 事件 11037
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                               企业单一登录                                                                                                               |
| 产品版本 |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    事件 ID     |                                                                                                                         11037                                                                                                                         |
|  事件源   |                                                                                                                        ENTSSO                                                                                                                         |
|    组件    |                                                                                                                          N/A                                                                                                                          |
|  符号名称  |                                                                                                              SSO_INFO_PS_MAPPING_INVALID                                                                                                              |
|  消息正文   | 外部密码更改。 未更改外部帐户的密码，因为映射不再有效。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |
  
## <a name="explanation"></a>解释  
 映射不再是“应用程序用户”组的一部分。  
  
## <a name="user-action"></a>用户操作  
 此消息列出了外部帐户和应用程序的名称。 您可以使用这一信息来查明映射不再有效的原因。