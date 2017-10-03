---
title: "计划程序无法计划批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ac6d79c-c995-4c95-a4da-ee2f50b9a13a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bef1df18d88f8497fde440383d63bc64eefdd69a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scheduler-was-unable-to-schedule-the-batch"></a>计划程序无法对批处理进行计划
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|-|  
|消息正文|计划程序无法对批处理进行计划|  
  
## <a name="explanation"></a>解释  
 此错误表明计划程序无法确定下次发生的批处理发布。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保批处理发布计划有效：  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。  
  
3.  右键单击正确方。  
  
4.  单击 **“属性”**。  
  
5.  在 [*方名称*]**参与方属性**对话框中，在左窗格中，单击**发送端口**。  
  
6.  发送端口中输入名称**发送端口**列表。  
  
7.  单击 **“确定”**。