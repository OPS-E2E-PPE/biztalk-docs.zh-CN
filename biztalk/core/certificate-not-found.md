---
title: 找不到证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629b199f-1884-4e88-beaa-a2e5c5e792e9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c18f112edc14375e6edc2aaa52c9e468d1bd39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232605"
---
# <a name="certificate-not-found"></a>找不到证书
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|找不到证书。|  
  
## <a name="explanation"></a>解释  
 找不到给定的搜索条件的证书。  

#### <a name="user-action"></a>用户操作
验证证书的搜索条件。 
  
## <a name="verify-search-criteria"></a>验证搜索条件  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 单击 **“编辑”**。  
  
10. 在**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分正确配置，以指示的有效证书。  
  
 对于 WCF 自定义和 WCF CustomIsolated 适配器，请确保中的搜索条件**证书引用**部分正确配置，以指示该证书中的有效证书**存储名称**.  
  
## <a name="verify-search-criteria-for-standard-wcf-adapters"></a>验证标准 WCF 适配器的搜索条件  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**安全**选项卡。  
  
9. 确保**指纹**为服务和客户端证书的属性指示在证书存储中的有效证书。  
  
10. 在“证书”管理单元中，确保为 WCF 传输安装有效的证书。  

## <a name="see-also"></a>另请参阅 
  
-   [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)  
  
