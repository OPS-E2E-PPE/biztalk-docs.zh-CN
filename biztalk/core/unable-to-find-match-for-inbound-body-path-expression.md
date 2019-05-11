---
title: 找不到入站的正文路径表达式的匹配项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9199b959c4a120f294ef5cf30739bafccf901690
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266480"
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a>找不到入站的正文路径表达式的匹配项
## <a name="details"></a>详细信息  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |       找不到入站的正文路径表达式的匹配项"{0}"消息中       |

## <a name="explanation"></a>解释  
 执行对传入消息的正文路径表达式未返回任何匹配项。  

## <a name="user-action"></a>用户操作  
 请确保正文路径表达式正确，并且传入消息具有正确的数据。  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择正确的端口。  

7. 单击**配置**。  

8. 在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**消息**选项卡。  

9. 在中**入站 BizTalk 消息正文**部分中，检查的信息**正文路径表达式**。
