---
title: 单一登录： 事件 10849 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdfb1cea-e445-4318-9891-b6b70a266ca9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cb1d63cf12c19a8e2213c7506f1752f86a02a85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991846"
---
# <a name="single-sign-on-event-10849"></a>单一登录： 事件 10849
## <a name="details"></a>详细信息  
  
|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  产品名称   |                            企业单一登录                             |
| 产品版本 |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    事件 ID     |                                      10849                                       |
|  事件源   |                                      ENTSSO                                      |
|    组件    |                                       N/A                                        |
|  符号名称  |                     ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE                      |
|  消息正文   | 无法创建指定了“直接密码同步”标志的应用程序。 |
  
## <a name="explanation"></a>解释  
 无法创建指定了“直接密码同步”标志的应用程序。  
  
## <a name="user-action"></a>用户操作  
 创建应用程序而无需直接密码同步标志。 然后添加并创建字段，启用该应用程序，再指定直接密码同步标志。