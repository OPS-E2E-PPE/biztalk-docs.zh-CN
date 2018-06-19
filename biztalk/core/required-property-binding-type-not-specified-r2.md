---
title: 所需的未指定属性绑定类型 (R2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a34de62453bd252e110edd0caf8a71996f25ae3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268805"
---
# <a name="required-property-binding-type-not-specified-r2"></a>未指定必需的属性绑定类型 (R2)
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|未指定所需的属性绑定类型|  
  
## <a name="explanation"></a>解释  
 配置 WCF-Custom 或 WCF-CustomIsolated 传输时，未设置“绑定类型”属性。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置绑定类型属性。  
  
#### <a name="to-configure-the-binding-type-property"></a>配置绑定类型属性的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF-[***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 中指定一个值**绑定类型**列表。  
  
 有关配置绑定的详细信息，请参阅以下资源：  
  
-   [如何配置 WCF CustomIsolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [如何配置 WCF 自定义接收位置](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [如何配置 WCF 自定义发送端口](../core/how-to-configure-a-wcf-custom-send-port.md)