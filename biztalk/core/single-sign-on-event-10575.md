---
title: 单一登录：Event 10575 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76cd29d85b700eadb0bce35822a2ab73493755c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295929"
---
# <a name="single-sign-on-event-10575"></a>单一登录：事件 10575
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                     企业单一登录                                                                                     |
| 产品版本 |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    事件 ID     |                                                                                               10575                                                                                               |
|  事件源   |                                                                                              ENTSSO                                                                                               |
|    组件    |                                                                                                不可用                                                                                                |
|  符号名称  |                                                                                  SSO_INFO_CHANGED_SECRET_SERVER                                                                                   |
|  消息正文   | 更新密钥服务器 name.%r<br /><br /> 新的服务器: %1 %r<br /><br /> 旧密钥服务器: %2 %r<br /><br /> 跟踪 ID: %3 %r<br /><br /> 客户端计算机: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 这是一条信息性消息，也可用于跟踪 SSO 系统中的发生的与安全相关的重要事件。 此消息表明已更新的服务器名称。  
  
## <a name="user-action"></a>用户操作  
 不需要任何用户操作。