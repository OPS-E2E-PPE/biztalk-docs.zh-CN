---
title: 无法导出服务终结点配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 795145fa-0ce4-498f-a82e-eb752a5f4764
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2418517b7695aedd5c80a950a9b74faf5d380346
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973350"
---
# <a name="unable-to-export-service-endpoint-configuration"></a>无法导出服务终结点配置
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |              无法导出到的服务终结点配置"{0}"              |
  
## <a name="explanation"></a>解释  
 此错误表示用户可能没有向目标写入数据的权限。 或者，未正确指定某些所需的属性，例如“地址(URI)”和“绑定类型”。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置终结点标识。  
  
#### <a name="to-configure-the-endpoint-identity"></a>配置终结点标识的步骤  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 确保允许向目标文件夹写入数据。  
  
10. 检查**行为**选项卡和**终结点标识**中的设置**常规**选项卡，以确保它们有效。  
  
    > [!NOTE]
    >  您必须对目标文件夹拥有写入权限。 联系计算机管理员获取这些权限。