---
title: 单一登录： 事件 10692 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37148a774504599b99665b57691316c35d0783bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987278"
---
# <a name="single-sign-on-event-10692"></a>单一登录： 事件 10692
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                                                      企业单一登录                                                                                                                      |
| 产品版本 |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    事件 ID     |                                                                                                                                10692                                                                                                                                |
|  事件源   |                                                                                                                               ENTSSO                                                                                                                                |
|    组件    |                                                                                                                                 N\A                                                                                                                                 |
|  符号名称  |                                                                                                                    SSO_WARN_REPLAY_ACCESS_DENIED                                                                                                                    |
|  消息正文   | 无法重播外部密码更改，因为原始调用方不再是适配器访问帐户的成员。%r<br /><br /> 重播文件: %1 %r<br /><br /> 适配器: %2 %r<br /><br /> 原始调用方: %3 %r<br /><br /> 访问帐户： %4 |

## <a name="explanation"></a>解释  
 此警告事件表明，SSO 已与 SSO 数据库重新建立了联系，但无法（在 SSO 数据库中）作出重播文件中指定的更改，因为最初指定该更改的帐户不再有效。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
