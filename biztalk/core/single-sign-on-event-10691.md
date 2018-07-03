---
title: 单一登录： 事件 10691 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fcefb49-c068-41e9-850d-99864c0899bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69acc99acd002f23d3d6e02430d58fb88f9651a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009894"
---
# <a name="single-sign-on-event-10691"></a>单一登录： 事件 10691
## <a name="details"></a>详细信息  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                          企业单一登录                                          |
| 产品版本 |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    事件 ID     |                                                    10691                                                    |
|  事件源   |                                                   ENTSSO                                                    |
|    组件    |                                                     N\A                                                     |
|  符号名称  |                                       SSO_ERROR_REPLAY_FILE_MISMATCH                                        |
|  消息正文   | 在重播 file.%r 中检测到损坏。<br /><br /> 重播文件: %1 %r<br /><br /> 其他数据： %2 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 已重建与 SSO 数据库的联系，但不能与相应的进度文件中打开重播文件由于不匹配。 如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

- 删除重播文件。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
