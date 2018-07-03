---
title: 单一登录： 事件 11061 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1733e444ecdfdaf54b20beb2de6894ade3466f4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011326"
---
# <a name="single-sign-on-event-11061"></a>单一登录： 事件 11061
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                     企业单一登录                                                                                                                     |
| 产品版本 |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    事件 ID     |                                                                                                                               11061                                                                                                                               |
|  事件源   |                                                                                                                              ENTSSO                                                                                                                               |
|    组件    |                                                                                                                                N/A                                                                                                                                |
|  符号名称  |                                                                                                                   SSO_WARN_BAD_PASSWORD_FILTER                                                                                                                    |
|  消息正文   | 密码筛选器字符串无效。 将不使用任何密码筛选器。%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 密码筛选器字符串: %2 %r<br /><br /> 处理标记数: %3 %r<br /><br /> 其他数据: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 已手动创建无效的密码筛选器。 此进程中的某点已引入错误（请参阅警告文本中的“密码筛选器字符串”以了解错误位置）。  
  
## <a name="user-action"></a>用户操作  
 若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。