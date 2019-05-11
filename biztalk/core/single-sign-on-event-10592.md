---
title: 单一登录：Event 10592 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bfd622db90bbafcb4d2af1b45ae2b2286e3345c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270948"
---
# <a name="single-sign-on-event-10592"></a>单一登录：事件 10592
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                             企业单一登录                                                              |
| 产品版本 |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    事件 ID     |                                                                       10592                                                                        |
|  事件源   |                                                                       ENTSSO                                                                       |
|    组件    |                                                                        不可用                                                                         |
|  符号名称  |                                                           SSO_WARN_TICKET_DECRYPT_FAILED                                                           |
|  消息正文   | 无法解密该票证。 票证无效或者它可能具有 expired.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 错误代码： %2 |
  
## <a name="explanation"></a>解释  
 票证无效或者可能已过期。  
  
## <a name="user-action"></a>用户操作  
 请确认你想要使用该票证有效，并且未过期。