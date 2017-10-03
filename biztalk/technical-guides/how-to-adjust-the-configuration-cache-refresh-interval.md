---
title: "如何调整配置缓存刷新间隔 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9459fadd65af220982ab31ae0e464cb7f1986e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>如何调整配置缓存刷新间隔
配置缓存刷新间隔定义在其中 BizTalk Server 更新的终结点配置的时间段。 当你启动 BizTalk Server 时，BizTalk 服务器管理，如 MessageBox 数据库、 服务器属性、 适配器、 和到跟踪数据库的连接中的所有项都存储在配置缓存。 通过配置刷新间隔来刷新其缓存中的所有项。 默认情况下这是每隔 60 秒，服务器数据库连接和服务器属性除外。 这意味着，如果更改为 BizTalk 组，如 SMTP 主机的常规属性所做的更改会选取在 60 秒内。 你对其进行刷新之前，不会反映所做的 BizTalk Server 管理控制台当前打开的实例之外的系统更改。  
  
 配置缓存刷新间隔是 BizTalk 组属性的一部分。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>若要调整缓存刷新间隔  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，右键单击**BizTalk 组**，然后单击**设置**。  
  
3.  在**BizTalk 设置仪表板**对话框中，选择**常规**选项卡。有关**配置刷新间隔**属性，键入或选择的时间 （以秒为单位） 中的所有项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理缓存必须等待配置缓存刷新间隔，然后单击**确定**.  
  
    > [!NOTE]  
    >  刷新所涉及的项包括 MessageBox 数据库、服务器属性、适配器以及跟踪数据库的连接。  
  
    > [!NOTE]  
    >  默认情况下，配置缓存中的所有对象都刷新每隔 60 秒，服务器数据库连接和服务器属性除外。