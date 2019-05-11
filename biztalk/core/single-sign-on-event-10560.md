---
title: 单一登录：Event 10560 | Microsoft Docs
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
ms.openlocfilehash: b43a9558cff9325cb7a5355213001d67a0218d43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296053"
---
# <a name="single-sign-on-event-10560"></a>单一登录：事件 10560
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                  企业单一登录                                                                                  |
| 产品版本 |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    事件 ID     |                                                                                            10560                                                                                            |
|  事件源   |                                                                                           ENTSSO                                                                                            |
|    组件    |                                                                                             不可用                                                                                             |
|  符号名称  |                                                                               SSO_ERROR_BACKUP_SECRET_FAILED                                                                                |
|  消息正文   | 备份主密钥 secrets.%r 失败<br /><br /> 文件名称: %1 %r<br /><br /> 当前 MSID: %2 %r<br /><br /> 上一个 MSID: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 错误代码： %5 |
  
## <a name="explanation"></a>解释  
 尝试备份主密钥失败。 用户尝试进行备份可能存在错误的权限、 路径或目录。  
  
## <a name="user-action"></a>用户操作  
 有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。