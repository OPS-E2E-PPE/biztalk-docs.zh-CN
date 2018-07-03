---
title: 单一登录： 事件 10675 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb383c6d-0c46-4752-b8f6-200e1cd9763e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 919ffcaac53af2f1dbbc5c0f21a769fc547d2782
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983702"
---
# <a name="single-sign-on-event-10675"></a>单一登录： 事件 10675
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                        企业单一登录                                                                                         |
| 产品版本 |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    事件 ID     |                                                                                                  10675                                                                                                   |
|  事件源   |                                                                                                  ENTSSO                                                                                                  |
|    组件    |                                                                                                   N\A                                                                                                    |
|  符号名称  |                                                                                      SSO_INFO_WINDOWS_PASSWORD_SET                                                                                       |
|  消息正文   | 在 SSO 数据库中成功更新了 Windows 密码。%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> Windows 帐户: %2 %r<br /><br /> 应用程序名称: %3 %r<br /><br /> 外部帐户： %4 |

## <a name="explanation"></a>解释  
 此信息事件表示在 SSO 数据库中成功更新了 Windows 密码。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [密码同步](../core/password-synchronization2.md)
