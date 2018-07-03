---
title: 单一登录： 事件 10818 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328e4286ed024923ab66e147e806ef5db5065b77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972430"
---
# <a name="single-sign-on-event-10818"></a>单一登录： 事件 10818
## <a name="details"></a>详细信息  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  产品名称   |                            企业单一登录                            |
| 产品版本 |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    事件 ID     |                                      10818                                      |
|  事件源   |                                     ENTSSO                                      |
|    组件    |                                       N/A                                       |
|  符号名称  |                         ENTSSO_E_AMBIGUOUS_SYNC_FIELDS                          |
|  消息正文   | 应用程序必须具有两个字段或者只有一个字段必须标记为同步。 |
  
## <a name="explanation"></a>解释  
 如果存在两个以上字段，则必须只对一个字段标记为密码同步。  
  
## <a name="user-action"></a>用户操作  
 若要纠正这种情况下，必须删除该应用程序并重新创建它，以便它遵循这些准则。