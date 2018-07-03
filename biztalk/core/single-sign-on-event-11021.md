---
title: 单一登录： 事件 11021 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70b987aa-8097-4243-a25b-f1cc12c5bc6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407bd65b0c7d97ad8b9213d22a093160ac312e10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019407"
---
# <a name="single-sign-on-event-11021"></a>单一登录： 事件 11021
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                          企业单一登录                                                                                                                                                                          |
| 产品版本 |                                                                                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                          |
|    事件 ID     |                                                                                                                                                                                    11021                                                                                                                                                                                    |
|  事件源   |                                                                                                                                                                                   ENTSSO                                                                                                                                                                                    |
|    组件    |                                                                                                                                                                                     N/A                                                                                                                                                                                     |
|  符号名称  |                                                                                                                                                           SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED                                                                                                                                                            |
|  消息正文   | 外部密码更改将导致另一外部帐户被更改。%r<br /><br /> 这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> Windows 帐户: %3 %r<br /><br /> 外部帐户 1: %4 %r<br /><br /> 外部帐户 2: %5 |
  
## <a name="explanation"></a>解释  
 这是一条信息性消息，指示外部密码更改将导致另一外部帐户被更改。  
  
## <a name="user-action"></a>用户操作  
 您应该立即确认是利用您的信息和授权做出的更改。 如果是这样，无需进行任何操作。 如果不是，请查明进行更改的位置，并确认此更改位于系统中的安全位置。