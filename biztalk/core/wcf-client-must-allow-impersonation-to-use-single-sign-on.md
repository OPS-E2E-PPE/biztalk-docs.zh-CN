---
title: WCF 客户端必须允许模拟才能使用单一登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5b9f294-4d8a-4a12-91e8-8d325db7c420
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f79cee850fac0689cbf956a966ad0970d36223f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279074"
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a>WCF 客户端必须允许模拟才能使用单一登录
## <a name="details"></a>详细信息  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |           WCF 客户端必须允许模拟才能使用单一登录            |

## <a name="explanation"></a>解释  
 在接收位置中启用单一登录 (SSO)，但 WCF 客户端不允许模拟。  

## <a name="user-action"></a>用户操作  
 请确保调用服务的 WCF 客户端允许模拟。  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择**WCF 自定义**(或**Wcf-customisolate**)。  

7. 单击**配置**。  

8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**行为**选项卡。  

9. 在中**行为**部分中，单击**ServiceAuthorization**。 在中**配置**部分中，该属性**ImpersonateCallerForAllOperations**应设置为**True**。  

10. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**其他**选项卡。  

11. 在凭据部分中，选择相应选项**使用单一登录**。
