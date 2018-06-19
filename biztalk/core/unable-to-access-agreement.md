---
title: 无法访问协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a28b2b3587781d66e8788ca88931c7c5522bac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286533"
---
# <a name="unable-to-access-agreement"></a>无法访问协议
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|UnableToLocateAS2PartyError|  
|消息正文|无法访问协议。 AS2From: {0} AS2To: {1}。 错误： {2}|  
  
## <a name="explanation"></a>解释  
 此错误表明 BizTalk Server 找不到给定限定符和值的参与方。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请为给定的限定符创建参与方别名：  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。  
  
3.  右键单击正确方。  
  
4.  单击 **“属性”**。  
  
5.  在 [*方名称*]**参与方属性**对话框框中，输入**EDIINT AS2 从值**中**名称**列。  
  
6.  输入中的方名称**值**列。  
  
7.  单击 **“确定”**。