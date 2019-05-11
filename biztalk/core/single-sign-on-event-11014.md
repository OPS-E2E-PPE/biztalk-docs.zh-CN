---
title: 单一登录：事件 11014 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aebd0225967e3165f19449b73488d8f938b349ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267272"
---
# <a name="single-sign-on-event-11014"></a>单一登录：事件 11014
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                企业单一登录                                                                 |
| 产品版本 |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    事件 ID     |                                                                          11014                                                                           |
|  事件源   |                                                                          ENTSSO                                                                          |
|    组件    |                                                                           不可用                                                                            |
|  符号名称  |                                                                  SSO_ERROR_ACCESS_CHECK                                                                  |
|  消息正文   | 访问检查 failed.%r<br /><br /> 客户端用户： %1\\%2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 其他数据: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 访问检查失败的客户端和应用程序列出。  
  
## <a name="user-action"></a>用户操作  
 其他信息应可以解决此问题。 若要避免此错误在将来，您可以降低审核级别。