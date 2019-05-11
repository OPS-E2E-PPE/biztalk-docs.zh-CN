---
title: 单一登录：事件 11034 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 828bc5fb-12ab-4eea-94f2-2434ad0ee033
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87f8b49a2834199cd3f206afedd22c2542422725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401037"
---
# <a name="single-sign-on-event-11034"></a>单一登录：事件 11034
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                                                                                企业单一登录                                                                                                                                                                                |
| 产品版本 |                                                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                |
|    事件 ID     |                                                                                                                                                                                          11034                                                                                                                                                                                          |
|  事件源   |                                                                                                                                                                                         ENTSSO                                                                                                                                                                                          |
|    组件    |                                                                                                                                                                                           不可用                                                                                                                                                                                           |
|  符号名称  |                                                                                                                                                                        SSO_INFO_PS_WIN_CHANGE_APP_INCORRECT_TYPE                                                                                                                                                                        |
|  消息正文   | Windows 密码更改。 已检测到此 Windows 帐户的映射，但被忽略，因为该应用程序不是正确的类型。 只有个人或组类型的应用程序支持 Windows 密码 sync.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序: %3 %r<br /><br /> 外部帐户: %4 %r<br /><br /> 客户端用户： %5 |
  
## <a name="explanation"></a>解释  
 只有个人或组类型的应用程序支持 Windows 密码同步。  
  
## <a name="user-action"></a>用户操作  
 有关详细信息，请参阅[密码同步](../core/password-synchronization2.md)。