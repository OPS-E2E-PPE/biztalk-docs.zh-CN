---
title: 单一登录：Event 11037 | Microsoft Docs
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
ms.openlocfilehash: 6d64605fbdd4cb470fc6dec060650bd78b581f84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401031"
---
# <a name="single-sign-on-event-11037"></a>单一登录：事件 11037
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                               企业单一登录                                                                                                               |
| 产品版本 |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    事件 ID     |                                                                                                                         11037                                                                                                                         |
|  事件源   |                                                                                                                        ENTSSO                                                                                                                         |
|    组件    |                                                                                                                          不可用                                                                                                                          |
|  符号名称  |                                                                                                              SSO_INFO_PS_MAPPING_INVALID                                                                                                              |
|  消息正文   | 外部密码更改。 密码未更改外部帐户因为映射不再 valid.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |
  
## <a name="explanation"></a>解释  
 映射不再是 Application Users 组的一部分。  
  
## <a name="user-action"></a>用户操作  
 此消息列出了外部帐户和应用程序的名称。 可以使用此信息来找出为什么映射不再有效。