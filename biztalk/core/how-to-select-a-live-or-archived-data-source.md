---
title: 如何选择实时或存档的数据源 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83f034a41fffa0c646b0173e8b889c20373760ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967150"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>如何选择实时或存档的数据源
使用 BizTalktracking 可以访问存档和实时数据。 从主选择实时或存档的数据源**BizTalk Server 管理**节点 BizTalk Server 管理控制台。  默认情况下将采用实时数据源，即从 BizTalk 管理数据库中检索数据。 如果选择使用存档的数据，则必须选择要使用的相应服务器和数据库。  

-   存档的数据：通过分析存档的数据，可以检查在业务和系统方面的趋势，因为您可以根据需要以前任意时候发生的事件进行查看。 若要选择存档的数据，则还必须选择包含存档数据的相应 SQL Server 和 SQL 数据库。  

     通过选择指定存档的数据**连接到现有跟踪数据库...**.  

-   实时数据：通过分析实时数据，可以监视业务流程和管道，以便确定并解决开发或过渡环境中的问题。 通过监视实时数据，还可以解决系统中的问题，例如，消息为何挂起等。  

     通过选择指定实时数据**连接到现有组...**.  

## <a name="prerequisites"></a>必要條件  
 必须以 BizTalk Server Operators 组成员的身份登录，才能执行此过程。  

### <a name="to-select-live-data"></a>选择实时数据  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 单击主**BizTalk Server 管理**节点。  

3. 单击**连接到现有组...**  

4. 在中**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。  

5. 在中**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。  

6. 单击“确定” 。  

### <a name="to-select-archived-data"></a>选择存档的数据  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 单击主**BizTalk Server 管理**节点。  

3. 单击**连接到现有跟踪数据库...**  

4. 在中**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。  

5. 在中**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。  

6. 单击“确定” 。
