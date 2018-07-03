---
title: 找到的证书无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b3a9ae8-a9d7-4025-bacd-443e136ff980
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a069ee0c934f9a7636646a07bd5a7f777d88c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020581"
---
# <a name="invalid-certificate-found"></a>找到的证书无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                             找到的证书无效                              |
  
## <a name="explanation"></a>解释  
 您为 WCF 传输提供的证书无效。  

#### <a name="user-action"></a>用户操作
添加证书。 
  
## <a name="add-a-certificate"></a>添加证书  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 单击 **“编辑”**。  
  
10. 在中**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分已正确配置，以显示有效证书。  
  
    对于 Wcf-custom 和 Wcf-customisolated 适配器，请确保中的搜索条件**证书引用**部分已正确配置，以指示该证书中的有效证书**存储区名称**.  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a>为标准 WCF 适配器添加证书  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**安全**选项卡。  
  
9. 絋粄**指纹**服务和客户端证书的属性显示在证书中的有效证书**存储区名称**。  
  
   在“证书”管理单元中，确保为 WCF 传输安装有效的证书。  
  
## <a name="see-also"></a>另请参阅 
  
[安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)  