---
title: 单一登录： 事件 10843 |Microsoft Docs
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
ms.openlocfilehash: 40b7e03f54d4c4ac2b7074d2aa13d771ce20a9e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012998"
---
# <a name="single-sign-on-event-10843"></a>单一登录： 事件 10843
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                      企业单一登录                                                                      |
| 产品版本 |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    事件 ID     |                                                                                10843                                                                                |
|  事件源   |                                                                               ENTSSO                                                                                |
|    组件    |                                                                                 N/A                                                                                 |
|  符号名称  |                                                                         ENTSSO_E_NO_SECRET2                                                                         |
|  消息正文   | 无法执行加密或解密，因为密钥不在主密钥服务器中。 有关相关错误，请参阅事件日志（在计算机 %1 上）。 |
  
## <a name="explanation"></a>解释  
 拒绝访问。  
  
## <a name="user-action"></a>用户操作  
 主密钥服务器脱机，或主密钥服务器缺少所需的主密钥。 参阅指定计算机上的事件日志，了解相关错误。