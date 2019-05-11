---
title: 单一登录：Event 10749 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25392ade6b6db955a3f5d1b99086f01f920f2ff1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395478"
---
# <a name="single-sign-on-event-10749"></a>单一登录：事件 10749
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                      企业单一登录                                                                                                                      |
| 产品版本 |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    事件 ID     |                                                                                                                                10749                                                                                                                                |
|  事件源   |                                                                                                                               ENTSSO                                                                                                                                |
|    组件    |                                                                                                                                 N\A                                                                                                                                 |
|  符号名称  |                                                                                                                       SSO_WARN_PS_CLIENT_PING                                                                                                                       |
|  消息正文   | 无法联系目标 SSO 服务器。<br /><br /> 检查 SSO 服务正在运行该服务器上并且它可以 contacted.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> SSO 服务器名称: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此警告事件表明 SSO 密码同步无法联系指定的目标 SSO 服务器。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 使用 ENTSSO 服务器管理单元中，若要检查的服务器。  

- 如果未运行，请启动企业单一登录服务。  

- 检查与目标 SSO 服务器的网络连接。  

- 请检查目标 SSO 服务器上的防火墙。  

  有关详细信息，请参阅下列资源：  

- [如何使用服务器管理单元](../core/how-to-use-the-servers-snap-in.md)
