---
title: 单一登录：事件 11036 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75adfa158082ca2a91c99948c172ef879c83bd13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401054"
---
# <a name="single-sign-on-event-11036"></a>单一登录：事件 11036
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                企业单一登录                                                                                                                                                                |
| 产品版本 |                                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                |
|    事件 ID     |                                                                                                                                                                          11036                                                                                                                                                                          |
|  事件源   |                                                                                                                                                                         ENTSSO                                                                                                                                                                          |
|    组件    |                                                                                                                                                                           不可用                                                                                                                                                                           |
|  符号名称  |                                                                                                                                                         SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC                                                                                                                                                          |
|  消息正文   | Windows 密码更改。 此 Windows 帐户的映射已检测到但被忽略，因为为此应用程序配置的适配器不支持对外部 systems.%r 密码同步<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 适配器: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 已检测到此 Windows 帐户的映射，但被忽略，因为为此应用程序配置的适配器不支持密码同步到外部系统。  
  
## <a name="user-action"></a>用户操作  
 检查适配器配置。  
  
 有关密码同步的信息，请参阅[密码同步](../core/password-synchronization2.md)。