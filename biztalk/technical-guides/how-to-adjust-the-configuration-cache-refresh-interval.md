---
title: 如何调整配置缓存刷新间隔 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99cffcba5181f62267ca9eeed9c9c3610ea7ee1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277165"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>如何调整配置缓存刷新间隔
配置缓存刷新间隔定义 BizTalk Server 中更新的终结点配置的时间段。 启动 BizTalk Server 时，BizTalk Server 管理，例如 MessageBox 数据库、 服务器属性、 适配器和到跟踪数据库的连接中的所有项都存储在配置缓存。 通过配置刷新间隔来刷新其缓存中的所有项。 默认情况下，这是每隔 60 秒，除服务器数据库连接和服务器属性。 这意味着，如果您更改为 BizTalk 组，如 SMTP 主机的常规属性所做的更改将选择 60 秒内。 你对其进行刷新之前，不会反映系统实例外部的当前打开的 BizTalk Server 管理控制台所做的更改。  
  
 配置缓存刷新间隔是 BizTalk 组属性的一部分。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>若要调整缓存刷新间隔  
  
1. 单击**启动**，单击**所有程序**，单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，右键单击**BizTalk 组**，然后单击**设置**。  
  
3. 在中**BizTalk 设置仪表板**对话框中，选择**常规**选项卡。有关**配置刷新间隔**属性，键入或选择的时间 （以秒为单位） 中的所有项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理缓存必须配置缓存刷新之间的等待，然后单击**确定**.  
  
   > [!NOTE]  
   >  在刷新中所涉及的项包括 MessageBox 数据库、 服务器属性、 适配器和跟踪数据库的连接。  
  
   > [!NOTE]  
   >  默认情况下，每 60 秒，除服务器数据库连接和服务器属性之外刷新配置缓存中的所有对象。