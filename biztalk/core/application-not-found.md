---
title: 未找到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d935ca74ce1fd6b8137807f14184d4fa22f3ade
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359038"
---
# <a name="application-not-found"></a>找不到应用程序
## <a name="details"></a>详细信息  

|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  产品名称   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| 产品版本 |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    事件 ID     |                                                    0                                                    |
|  事件源   |                                                    0                                                    |
|    组件    |                                                    0                                                    |
|  符号名称  |                                                    0                                                    |
|  消息正文   | 应用程序"{0}"找不到。验证应用程序的默认 BizTalk 配置数据库中存在 |

## <a name="explanation"></a>解释  
 此错误表示 BizTalk 使用的 BizTalk 数据库中不存在的应用程序。  

## <a name="user-action"></a>用户操作  
 使用以下过程配置有效的应用程序。  

#### <a name="to-configure-a-valid-application"></a>若要配置有效的应用程序  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 请确保该应用程序存在。 如果没有，请选择其他有效应用程序。
