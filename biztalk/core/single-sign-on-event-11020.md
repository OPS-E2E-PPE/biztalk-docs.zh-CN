---
title: 单一登录： 事件 11020 |Microsoft Docs
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
ms.openlocfilehash: 140a160ecf96cefdb8c19db87e53218d731f4362
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997558"
---
# <a name="single-sign-on-event-11020"></a>单一登录： 事件 11020
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                        企业单一登录                                                                                                                                                                        |
| 产品版本 |                                                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    事件 ID     |                                                                                                                                                                                  11020                                                                                                                                                                                  |
|  事件源   |                                                                                                                                                                                 ENTSSO                                                                                                                                                                                  |
|    组件    |                                                                                                                                                                                   N/A                                                                                                                                                                                   |
|  符号名称  |                                                                                                                                                          SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED                                                                                                                                                           |
|  消息正文   | Windows 密码更改将导致不同的 Windows 帐户更改。%r<br /><br /> 这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 外部帐户: %3 %r<br /><br /> Windows 帐户 1: %4 %r<br /><br /> Windows 帐户 2: %5 |
  
## <a name="explanation"></a>解释  
 此信息消息表示，Windows 密码更改将导致不同的 Windows 帐户更改。  
  
## <a name="user-action"></a>用户操作  
 您应该立即确认是利用您的信息和授权做出的更改。 如果是这样，无需进行任何操作。 如果不是，请查明进行更改的位置，并确认此更改位于系统中的安全位置。