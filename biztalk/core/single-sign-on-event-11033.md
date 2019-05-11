---
title: 单一登录：事件 11033 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed8e984-2b6c-4a9e-8603-175fdcabeb0a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9c77a8d8ea41a12e8b122dc21e4f0b8d3adce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303408"
---
# <a name="single-sign-on-event-11033"></a>单一登录：事件 11033
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                   企业单一登录                                                                                                                                   |
| 产品版本 |                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                   |
|    事件 ID     |                                                                                                                                             11033                                                                                                                                             |
|  事件源   |                                                                                                                                            ENTSSO                                                                                                                                             |
|    组件    |                                                                                                                                              不可用                                                                                                                                              |
|  符号名称  |                                                                                                                              SSO_INFO_PS_WIN_CHANGE_APP_DISABLED                                                                                                                              |
|  消息正文   | Windows 密码更改。 已检测到但被忽略，因为应用程序被 disabled.%r 此 Windows 帐户的映射<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 已检测到此 Windows 帐户的映射，但被忽略，因为禁用该应用程序。  
  
## <a name="user-action"></a>用户操作  
 若要使应用程序，请参阅[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md)。