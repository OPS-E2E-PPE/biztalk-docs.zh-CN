---
title: 单一登录： 事件 10528 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d96c1645-70f4-4d15-a0d7-0ae37669ad2a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2e91944de7399f8bee3e03f3facdb91263d2761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974822"
---
# <a name="single-sign-on-event-10528"></a>单一登录： 事件 10528
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                         企业单一登录                                                                          |
| 产品版本 |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    事件 ID     |                                                                                   10528                                                                                    |
|  事件源   |                                                                                   ENTSSO                                                                                   |
|    组件    |                                                                                    N\A                                                                                     |
|  符号名称  |                                                                           SSO_INFO_REENCRYPT_OK                                                                            |
|  消息正文   | 已成功完成 SSO 数据库重新加密。%r<br /><br /> 重新加密的凭据数: %1 %r<br /><br /> 当前 MSID: %2 %r<br /><br /> 上一个 MSID: %3 |

## <a name="explanation"></a>解释  
 此信息性事件表示 SSO 数据库的重新加密已经成功完成。  

## <a name="user-action"></a>用户操作  

- 不需要用户进行任何操作。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md)  

- [如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)
