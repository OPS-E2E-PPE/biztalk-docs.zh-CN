---
title: 单一登录：Event 10697 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18e8ba525f742226f2f38efd285dd58f6896e24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397312"
---
# <a name="single-sign-on-event-10697"></a>单一登录：事件 10697
## <a name="details"></a>详细信息  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                           企业单一登录                                           |
| 产品版本 |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    事件 ID     |                                                     10697                                                     |
|  事件源   |                                                    ENTSSO                                                     |
|    组件    |                                                      N\A                                                      |
|  符号名称  |                                       SSO_ERROR_PROGRESS_FILE_MISMATCH                                        |
|  消息正文   | 进度 file.%r 中检测到损坏。<br /><br /> 重播文件: %1 %r<br /><br /> 其他数据： %2 |

## <a name="explanation"></a>解释  
 此错误事件表示 SSO 已重建与 SSO 数据库的联系，但无法使用相应的重播文件由于不匹配打开进度文件。 如果 SSO 无法打开进度文件，它将开始第一个重播文件的开始记录。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查有相关事件的系统和应用程序事件日志。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
