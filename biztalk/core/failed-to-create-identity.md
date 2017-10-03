---
title: "无法创建标识 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 531f1057-1b6d-40ae-bf2f-a36baf4e0341
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 246db2e9546fbbea3db07cbaa5267f57936dfa14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="failed-to-create-identity"></a>未能创建标识
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|此错误表明适配器无法创建终结点标识。|  
  
## <a name="explanation"></a>解释  
 此错误表明适配器无法创建终结点标识。  
  
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
  
8.  在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。  
  
9. 在**终结点标识**部分中，单击**编辑**。  
  
10. 在**标识编辑器**对话框框中，确保设置有效。