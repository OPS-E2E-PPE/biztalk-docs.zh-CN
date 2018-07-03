---
title: 地址无效 (相对 uri 需要斜杠 (&quot;-&quot;)) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1376f924-f119-4ba8-9be1-eea7ba5f3eb6
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39a0e45cf540b07f167f2ca2a2ffcb52851e0327
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023531"
---
# <a name="invalid-address-relative-uri-needs-slash-quot-quot"></a>地址无效 (相对 uri 需要斜杠 (&quot;-&quot;))
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |         地址无效；应为以斜杠（“/”）开头的相对 URI          |
  
## <a name="explanation"></a>解释  
 您未提供一个相对地址格式正确的独立 WCF 接收位置。 例如，http://localhost/svc不能作为相对地址。 您不能将独立 WCF 接收位置的地址属性设置为绝对地址。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置地址。  
  
#### <a name="to-configure-an-address"></a>配置地址  
  
1. 单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序并找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 在中**地址 (URI)** 文字框中，更改的地址。 例如，正确格式的相对地址为 /path/service.svc。  
  
   有关接收位置的其他信息，请参阅以下内容：  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [如何配置 Wcf-wshttp 接收位置](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [如何配置 Wcf-basichttp 接收位置](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)