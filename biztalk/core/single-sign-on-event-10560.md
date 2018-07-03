---
title: 单一登录： 事件 10560 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82f9245b4eda9b6bf567aae1de2071d3e77aae04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967750"
---
# <a name="single-sign-on-event-10560"></a>单一登录： 事件 10560
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                  |
| 产品版本 |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            10560                                                                                            |
|  事件源   |                                                                                           ENTSSO                                                                                            |
|    组件    |                                                                                             N/A                                                                                             |
|  符号名称  |                                                                               SSO_ERROR_BACKUP_SECRET_FAILED                                                                                |
|  消息正文   | 备份主密钥失败。%r<br /><br /> 文件名称: %1 %r<br /><br /> 当前 MSID: %2 %r<br /><br /> 上一个 MSID: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 尝试备份主密钥失败。 尝试进行备份的用户的权限不正确，或使用的路径或目录不正确。  
  
## <a name="user-action"></a>用户操作  
 有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。