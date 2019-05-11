---
title: 单一登录：事件 11061 |Microsoft Docs
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
ms.openlocfilehash: 5da9ae664cd16a9fe6fe528650775877bd2322f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258745"
---
# <a name="single-sign-on-event-11061"></a>单一登录：事件 11061
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                     企业单一登录                                                                                                                     |
| 产品版本 |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    事件 ID     |                                                                                                                               11061                                                                                                                               |
|  事件源   |                                                                                                                              ENTSSO                                                                                                                               |
|    组件    |                                                                                                                                不可用                                                                                                                                |
|  符号名称  |                                                                                                                   SSO_WARN_BAD_PASSWORD_FILTER                                                                                                                    |
|  消息正文   | 密码筛选器字符串无效。 任何密码筛选器将不 used.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 密码筛选器字符串: %2 %r<br /><br /> 处理标记数: %3 %r<br /><br /> 其他数据: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 已手动创建无效的密码筛选器。 在此过程中的某个时候引入错误 （错误的位置的警告文本中，请参阅密码筛选器字符串）。  
  
## <a name="user-action"></a>用户操作  
 若要创建密码筛选器使用创建密码筛选器向导，请参阅[如何使用密码筛选器](../core/how-to-use-password-filters.md)。