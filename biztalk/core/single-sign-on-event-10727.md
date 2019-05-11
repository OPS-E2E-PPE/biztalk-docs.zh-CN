---
title: 单一登录：Event 10727 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ff7ac94-6f1e-4e56-853e-efc50b1fa1b6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4a6dcf108030a1679601e7c7a39a0f09b13d81a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65259011"
---
# <a name="single-sign-on-event-10727"></a>单一登录：事件 10727
## <a name="details"></a>详细信息  

|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                        企业单一登录                                                         |
| 产品版本 |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    事件 ID     |                                                                  10727                                                                   |
|  事件源   |                                                                  ENTSSO                                                                  |
|    组件    |                                                                   N\A                                                                    |
|  符号名称  |                                                      SSO_WARN_REPLAY_RECORD_FAILED                                                       |
|  消息正文   | 重播存储的外部密码更改 failed.%r<br /><br /> 适配器: %1 %r<br /><br /> 文件名称: %2 %r<br /><br /> 错误代码： %3 |

## <a name="explanation"></a>解释  
 此警告表明，SSO 无法重播在重播文件中记录的密码更改。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
