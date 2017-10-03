---
title: "无法访问方使用发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa582319226b114720ef234b8e3f65e416a94d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-party-using-send-port"></a>无法使用发送端口访问参与方
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|UnableToLocateAS2PartyBySendPortNameError|  
|消息正文|无法访问方使用发送端口： {0}|  
  
## <a name="explanation"></a>解释  
 此错误表明发送管道找不到与为传出的 AS2 消息指定的发送端口关联的参与方。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请将某个参与方与指定的发送端口关联：  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。  
  
3.  右键单击正确方。  
  
4.  单击 **“属性”**。  
  
5.  在 [*方名称*]**参与方属性**对话框中，在左窗格中，单击**发送端口**。  
  
6.  发送端口中输入名称**发送端口**列表。  
  
7.  单击 **“确定”**。