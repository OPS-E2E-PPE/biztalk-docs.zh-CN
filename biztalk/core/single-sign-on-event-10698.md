---
title: 单一登录： 事件 10698 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aacd272480ddb58de38960ae8dc1a744815ced64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966470"
---
# <a name="single-sign-on-event-10698"></a>单一登录： 事件 10698
## <a name="details"></a>详细信息  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  产品名称   |                      企业单一登录                       |
| 产品版本 |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    事件 ID     |                                10698                                 |
|  事件源   |                                ENTSSO                                |
|    组件    |                                 N\A                                  |
|  符号名称  |                     SSO_INFO_REPLAY_FILE_DELETED                     |
|  消息正文   | 重播或进度文件已 deleted.%r<br /><br /> 文件名称： %1 |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 已删除重播和 \ 或进度文件。  

 ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。 进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
