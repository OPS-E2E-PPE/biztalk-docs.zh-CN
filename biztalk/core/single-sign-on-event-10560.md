---
title: "单一登录： 事件 10560 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d630dccdd21aaade843d4aa8fd7026d05fd71da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10560"></a>单一登录： 事件 10560
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10560|  
|事件源|ENTSSO|  
|组件|N/A|  
|符号名称|SSO_ERROR_BACKUP_SECRET_FAILED|  
|消息正文|备份主密钥失败。%r<br /><br /> 文件名: %1 %r<br /><br /> 当前 MSID: %2 %r<br /><br /> 上一个 MSID: %3 %r<br /><br /> 客户端用户: %4 %r<br /><br /> 错误代码： %5|  
  
## <a name="explanation"></a>解释  
 尝试备份主密钥失败。 尝试进行备份的用户的权限不正确，或使用的路径或目录不正确。  
  
## <a name="user-action"></a>用户操作  
 有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。