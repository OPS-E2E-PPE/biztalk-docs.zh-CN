---
title: 单一登录：Event 10843 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847e464e-5733-4703-905f-d44a4c4f5cc3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8389a1b6443fbe2d4abe592b305508b2780afdf6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307307"
---
# <a name="single-sign-on-event-10843"></a>单一登录：事件 10843
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                      企业单一登录                                                                      |
| 产品版本 |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    事件 ID     |                                                                                10843                                                                                |
|  事件源   |                                                                               ENTSSO                                                                                |
|    组件    |                                                                                 不可用                                                                                 |
|  符号名称  |                                                                         ENTSSO_E_NO_SECRET2                                                                         |
|  消息正文   | 无法执行加密或解密，因为密钥不能从主密钥服务器。 请参阅事件日志中 （在计算机"%1"） 相关的错误。 |
  
## <a name="explanation"></a>解释  
 拒绝访问。  
  
## <a name="user-action"></a>用户操作  
 主密钥服务器脱机，或在主密钥服务器缺少所需的主密钥。 有关相关错误指定的计算机上，请参阅事件日志。