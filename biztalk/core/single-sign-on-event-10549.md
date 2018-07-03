---
title: 单一登录： 事件 10549 |Microsoft Docs
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
ms.openlocfilehash: 18a3b92192c7e7e4a0906bfd35e4069dd3481d45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993438"
---
# <a name="single-sign-on-event-10549"></a>单一登录： 事件 10549
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                企业单一登录                                                                                 |
| 产品版本 |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                |
|    事件 ID     |                                                                                          10549                                                                                           |
|  事件源   |                                                                                          ENTSSO                                                                                          |
|    组件    |                                                                                            CO                                                                                            |
|  符号名称  |                                                                             SSO_ERROR_CREATE_DATABASE_FAILED                                                                             |
|  消息正文   | 创建并初始化该 SSO 数据库失败。%r<br /><br /> SQL Server 名称: %1 %r<br /><br /> SSO 数据库名称: %2 %r<br /><br /> 客户端用户: %3 %r<br /><br /> 错误代码： %4 |

## <a name="explanation"></a>解释  
 此错误表示创建和初始化 SSO 数据库的失败。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  

- 查看系统和应用程序事件日志了解相关消息。  

- 再次运行 Setup。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [安装 SSO](../core/installing-sso.md)
