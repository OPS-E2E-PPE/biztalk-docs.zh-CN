---
title: 单一登录：Event 10549 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac97f659dfc1f3b152df36c136fc45c3ef4238d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243376"
---
# <a name="single-sign-on-event-10549"></a>单一登录：事件 10549
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                企业单一登录                                                                                 |
| 产品版本 |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    事件 ID     |                                                                                          10549                                                                                           |
|  事件源   |                                                                                          ENTSSO                                                                                          |
|    组件    |                                                                                            CO                                                                                            |
|  符号名称  |                                                                             SSO_ERROR_CREATE_DATABASE_FAILED                                                                             |
|  消息正文   | 创建和初始化 SSO 数据库 failed.%r<br /><br /> SQL Server 名称: %1 %r<br /><br /> SSO 数据库名称: %2 %r<br /><br /> 客户端用户: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此错误表示创建和初始化 SSO 数据库失败。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 检查系统和应用程序事件日志中的关联消息。  

- 再次运行安装程序。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [安装 SSO](../core/installing-sso.md)
