---
title: 单一登录：Event 11020 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa6a0d72-ece6-4094-9263-dbf69bb068c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb1b87404bff9223935f17fd67e02c32de1bd2a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266355"
---
# <a name="single-sign-on-event-11020"></a>单一登录：事件 11020
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                        企业单一登录                                                                                                                                                                        |
| 产品版本 |                                                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    事件 ID     |                                                                                                                                                                                  11020                                                                                                                                                                                  |
|  事件源   |                                                                                                                                                                                 ENTSSO                                                                                                                                                                                  |
|    组件    |                                                                                                                                                                                   不可用                                                                                                                                                                                   |
|  符号名称  |                                                                                                                                                          SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED                                                                                                                                                           |
|  消息正文   | Windows 密码更改将导致不同的 Windows 帐户 changed.%r<br /><br /> 这允许，因为此外部系统的适配器配置为允许映射 conflicts.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> Windows 帐户 1: %4 %r<br /><br /> Windows 帐户 2: %5 |
  
## <a name="explanation"></a>解释  
 这是一条信息性消息，指出 Windows 密码更改将导致不同的 Windows 帐户进行更改。  
  
## <a name="user-action"></a>用户操作  
 您应该立即确认此更改为了与您的知识和授权。 如果是这样，不不需要任何操作。 如果没有，找出其中更改启动，并确认它已在系统中的安全位置。