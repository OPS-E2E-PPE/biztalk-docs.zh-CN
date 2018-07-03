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
ms.openlocfilehash: a861b6a4b4bc3f60dc2d3a50cb1c27d47e07b46a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985654"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a>如何调整配置缓存刷新间隔
配置缓存刷新间隔定义 BizTalk Server 中更新的终结点配置的时间段。 启动 BizTalk Server 时，BizTalk Server 管理，例如 MessageBox 数据库、 服务器属性、 适配器和到跟踪数据库的连接中的所有项都存储在配置缓存。 通过配置刷新间隔来刷新其缓存中的所有项。 默认情况下，这是每隔 60 秒，除服务器数据库连接和服务器属性。 这意味着，如果您更改为 BizTalk 组，如 SMTP 主机的常规属性所做的更改将选择 60 秒内。 你对其进行刷新之前，不会反映系统实例外部的当前打开的 BizTalk Server 管理控制台所做的更改。  
  
 配置缓存刷新间隔是 BizTalk 组属性的一部分。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-adjust-the-cache-refresh-interval"></a>若要调整缓存刷新间隔  
  
1. 单击**启动**，单击**所有程序**，单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，右键单击**BizTalk 组**，然后单击**设置**。  
  
3. 在中**BizTalk 设置仪表板**对话框中，选择**常规**选项卡。有关**配置刷新间隔**属性，键入或选择的时间 （以秒为单位） 中的所有项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理缓存必须配置缓存刷新之间的等待，然后单击**确定**.  
  
   > [!NOTE]  
   >  刷新所涉及的项包括 MessageBox 数据库、服务器属性、适配器以及跟踪数据库的连接。  
  
   > [!NOTE]  
   >  默认情况下，每 60 秒，除服务器数据库连接和服务器属性之外刷新配置缓存中的所有对象。