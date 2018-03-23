---
title: BizTalk 消息正文元素编码无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b407e5c3-4655-4b2f-8ecc-30eb080ec47c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1835371e5c042d3ddc46558cbf97970f6bfc6c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="biztalk-message-body-element-encoding-is-invalid"></a>BizTalk 消息正文元素编码无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|產品名稱|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|產品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|BizTalk 消息正文元素编码“{0}”无效。 预期编码:"xml"，"base64"，"十六进制"或"string"|  
  
## <a name="explanation"></a>解释  
 此错误表示对传出消息使用了 BizTalk 正文模板选项，但是，为 BizTalk 正文指定的编码类型无效。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置编码类型。  
  
#### <a name="to-configure-the-encoding-type"></a>配置编码类型的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口 **类型** 列表中，选择正确的端口。  
  
7.  单击 **配置**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**消息**选项卡。  
  
9. 在 **出站 WCF 消息正文** 部分中，单击 **模板-指定通过模板内容** 单选按钮。 在 **XML** 文本框中，BizTalk 正文的格式应为   
    \<**bts 消息正文 xmlns ="http://www.microsoft.com/schemas/bts2007"编码 ="[xml&#124;base64&#124;十六进制&#124;字符串]"/** \> (区分大小写，编码的有效值为 xml&#124;base64&#124;十六进制&#124;字符串)