---
title: 未指定所需的关联应用程序名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3e82a39-b052-4702-bfe2-700756a0ee6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef35502a6aaec322bc56ed9031cf0045d4bab1e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268008"
---
# <a name="required-affiliate-application-name-not-specified"></a>未指定所需的关联应用程序名称
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                 未指定所需的关联应用程序名称                  |
  
## <a name="explanation"></a>解释  
 **使用单一登录**选择选项，但尚未指定关联应用程序名称。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置关联应用程序名称。  
  
#### <a name="to-configure-the-affiliate-application-name"></a>若要配置关联应用程序名称  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**BizTalk 应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择**WCF 自定义**。  
  
7. 单击**配置**。  
  
8. 在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡。  
  
9. 在中**用户名凭据**部分中，为指定值**关联应用程序**。  
  
   有关创建 SSO 关联应用程序，请参阅 [http://go.microsoft.com/fwlink/?LinkId=94347](http://go.microsoft.com/fwlink/?LinkId=94347)