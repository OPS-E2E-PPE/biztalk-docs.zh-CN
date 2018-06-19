---
title: 无法导出服务终结点配置 |Microsoft 文档
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
ms.openlocfilehash: c3b36fa47d9302f3f88f65575bfa8f74c6469e9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286877"
---
# <a name="unable-to-export-service-endpoint-configuration"></a>无法导出服务终结点配置
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|无法将服务终结点配置导出到“{0}”|  
  
## <a name="explanation"></a>解释  
 此错误表示用户可能没有向目标写入数据的权限。 或者，未正确指定某些所需的属性，例如“地址(URI)”和“绑定类型”。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置终结点标识。  
  
#### <a name="to-configure-the-endpoint-identity"></a>配置终结点标识的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在 WCF **[***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 确保允许向目标文件夹写入数据。  
  
10. 检查**行为**选项卡和**终结点标识**中的设置**常规**选项卡，以确保它们都有效。  
  
    > [!NOTE]
    >  您必须对目标文件夹拥有写入权限。 联系计算机管理员获取这些权限。