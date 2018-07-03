---
title: 证书引用不明确 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a6a60d-97e6-4c60-86be-83efb4a50f99
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ac43f85b590ede746bbd14065d8e01701d1e91f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988830"
---
# <a name="ambiguous-certificate-reference"></a>证书引用不明确
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |       证书引用不明确，找到了多个有效证书       |
  
## <a name="explanation"></a>解释  
 找到了多个有效证书。  
  
#### <a name="user-action"></a>用户操作  
 验证只有一个配置有效的证书。  
  
## <a name="verify-certificate"></a>验证证书 
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 单击 **“编辑”**。  
  
10. 在中**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分已正确配置，以指示证书中的只有一个证书**应用商店名称**。  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a>对于 Wcf-custom 和 Wcf-customisolated 适配器验证证书  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**行为**选项卡。  
  
9. 确保中的搜索条件**证书引用**部分已正确配置，以指示证书中的只有一个证书**存储区名称**。  
  
10. 在“证书”管理单元中，确保只为您配置为 WCF 传输的搜索条件安装了一个证书。  
  
## <a name="see-also"></a>另请参阅
[安装用于 WCF 适配器的证书](../core/installing-certificates-for-the-wcf-adapters.md)  
 