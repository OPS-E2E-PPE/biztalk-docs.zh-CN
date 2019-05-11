---
title: 无法获取数据库或服务器名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 720e84c9d2305b85ec79f76873778e476f670900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354344"
---
# <a name="could-not-get-the-database-or-the-server-names"></a>无法获取数据库或服务器名称
## <a name="details"></a>详细信息  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |                     无法获取数据库或服务器名称                     |

## <a name="explanation"></a>解释  
 此错误表明 BizTalk 无法读取 BizTalkMgmtDb 名称和服务器名称从注册表。 此错误的一个可能的原因是未配置 BizTalk 组。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，配置 BizTalk 组：  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  

3. 右键单击**BizTalk 组**。  

4. 单击 **“属性”**。  

5. 在左窗格中，单击**常规**。  

6. 验证是否**服务器**名称和**数据库**名称是否正确。
