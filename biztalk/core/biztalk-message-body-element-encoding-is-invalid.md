---
title: BizTalk 消息正文元素编码无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bca7046606461dd3368224364c21dd48ea5dfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967966"
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a>BizTalk 消息正文元素编码无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  产品名称   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| 产品版本 |                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                           |
|    事件 ID     |                                                       0                                                        |
|  事件源   |                                                       0                                                        |
|    组件    |                                                       0                                                        |
|  符号名称  |                                                       0                                                        |
|  消息正文   | BizTalk 消息正文元素编码"{0}"无效。 希望的编码:"xml"，"base64"、"hex"或"string" |
  
## <a name="explanation"></a>解释  
 此错误表示对传出消息使用了 BizTalk 正文模板选项，但是，为 BizTalk 正文指定的编码类型无效。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置编码类型。  
  
#### <a name="to-configure-the-encoding-type"></a>配置编码类型的步骤  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**消息**选项卡。  
  
9. 在中**出站 WCF 消息正文**部分中，单击**模板-由模板指定的内容**单选按钮。 在中**XML**文本框中，BizTalk 正文的格式应为   
    \<**bts 消息正文 xmlns ="<http://www.microsoft.com/schemas/bts2007>"编码 ="[xml&#124;base64&#124;hex&#124;字符串]"/** \> (区分大小写，编码的有效值为 xml&#124;base64&#124;十六进制&#124;字符串)