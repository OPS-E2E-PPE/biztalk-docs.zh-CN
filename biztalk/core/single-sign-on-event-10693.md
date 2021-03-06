---
title: 单一登录：Event 10693 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 672bac7d-0ccc-4a42-a49d-57e387f4cf3a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cef53efa210d38d145dd4859fd3363e853a71fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397356"
---
# <a name="single-sign-on-event-10693"></a>单一登录：事件 10693
## <a name="details"></a>详细信息  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  产品名称   |                                       企业单一登录                                        |
| 产品版本 |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    事件 ID     |                                                 10693                                                  |
|  事件源   |                                                 ENTSSO                                                 |
|    组件    |                                                  N\A                                                   |
|  符号名称  |                                    SSO_WARNING_REPLAY_CANNOT_CREATE                                    |
|  消息正文   | 无法创建重播文件或进度 file.%r<br /><br /> 文件名称: %1 %r<br /><br /> 错误代码： %2 |

## <a name="explanation"></a>解释  
 此警告事件表示 SSO 无法与 SSO 数据库的连接丢失时创建重播和 \ 或进度文件。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
