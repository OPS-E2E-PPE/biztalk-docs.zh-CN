---
title: 指定必需的客户端证书指纹不 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19307bdb-29d7-4a79-9472-dda24dd8b263
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bea510fba1a9c4ab972229042e7af1e22cc2ad8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993470"
---
# <a name="required-client-certificate-thumbprint-not-specified"></a>未指定必需的客户端证书指纹
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |               未指定所需的客户端证书指纹。                |
  
## <a name="explanation"></a>解释  
 您未设置 WCF 发送端口的安全设置所需的客户端证书属性。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置 WCF 发送端口的安全设置。  
  
#### <a name="to-configure-security-settings"></a>配置安全设置  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**安全**选项卡。  
  
9. 絋粄**客户端证书**配置属性。  
  
   有关证书的其他信息，请参阅以下资源：  
  
-   [安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)