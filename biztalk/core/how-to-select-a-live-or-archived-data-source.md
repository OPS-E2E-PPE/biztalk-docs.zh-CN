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
ms.openlocfilehash: e5917c4488e047a1956fde66a659754c659f23d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383951"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>如何选择实时或存档的数据源
使用 biztalktracking 可以访问存档和实时数据。 从主选择实时或存档的数据源**BizTalk Server 管理**节点 BizTalk Server 管理控制台。  默认源是从 BizTalk 管理数据库中检索到的实时数据。 如果您选择使用存档的数据，必须选择相应服务器和数据库/s 可处理的。  

-   存档的数据：分析已存档的数据，可以在业务中和在系统上检查趋势，因为您可以根据需要回溯。 如果选择存档的数据，还必须选择相应的 SQL 服务器和包含已存档的数据的 SQL 数据库。  

     通过选择指定存档的数据**连接到现有跟踪数据库...**.  

-   实时数据：分析实时数据，可以监视业务流程和管道，以便确定并解决开发或过渡环境中的问题。 监视实时数据还可以在系统中，如挂起消息的原因更正问题。  

     通过选择指定实时数据**连接到现有组...**.  

## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的 BizTalk Server Operators 组的成员身份登录。  

### <a name="to-select-live-data"></a>选择实时数据  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 单击主**BizTalk Server 管理**节点。  

3. 单击**连接到现有组...**  

4. 在中**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。  

5. 在中**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。  

6. 单击“确定” 。  

### <a name="to-select-archived-data"></a>若要选择存档的数据  

1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 单击主**BizTalk Server 管理**节点。  

3. 单击**连接到现有跟踪数据库...**  

4. 在中**SQL Server 名称**框中，键入承载 BizTalk 管理数据库的服务器的名称。  

5. 在中**数据库名称**下拉列表框中，选择**BizTalkMgmtDb**。  

6. 单击“确定” 。
