---
title: 未知或意外的绑定元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56021ff3-5abf-46ab-90bb-4531ccc9abd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bfe15cf5aeab233c4ecef56f7b278e0646de5ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015638"
---
# <a name="unknown-or-unexpected-binding-element"></a>未知或意外的绑定元素
## <a name="details"></a>详细信息  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                       未知或意外的绑定元素                        |

## <a name="explanation"></a>解释  
 此错误表明适配器找不到绑定中指定的用户定义的绑定元素。 主要与 Wcf-custom 和 Wcf-customisolated 适配器出现这种情况。  

## <a name="user-action"></a>用户操作  
 使用以下过程验证绑定元素是否有效。  

#### <a name="to-verify-binding-elements-are-valid"></a>验证绑定元素是否有效  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择正确的端口。  

7. 单击**配置**。  

8. 在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。  

9. 确保配置中指定的绑定元素有效。
