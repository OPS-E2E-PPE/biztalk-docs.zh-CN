---
title: 门户主页上 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60072c30-d57b-4bd8-a7ee-b4d0fa50de58
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c2c525fdc8e5786143e8b4f942f0f2379226d3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295037"
---
# <a name="portal-home-page"></a>门户主页
图 1 显示主页，其中包含四个部分：  
  
-   **图表**部分按应用程序，按类型和分析随着时间推移，从应用程序的角度整个企业的总体运行状况，该值指示包含错误的细分。  
  
-   **注册表**部分包含的新请求发送到通用、 描述、 发现和集成 (UDDI) 服务的服务终结点发布列表。  
  
-   **警报历史记录**部分显示警报服务接收的警报的列表。  
  
-   **错误**部分显示由 ESB 失败业务流程异常路由机制和 BizTalk 失败消息路由机制生成的最新错误的简短的列表。 列表显示分组应用程序的错误，并显示在列表中的严重性、 服务名称、 错误类型的日期和时间每个错误。  
  
 ![门户主页上](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **图 1**  
  
 **ESB 管理门户的主页页面**  
  
 以下列表说明如何使用 ESB 管理门户主页的功能。  
  
-   当你首次加载主页上时，你可能无法看到的第一个图表中的任何应用程序。 若要选择你想要查看的信息的应用程序，请单击**选择应用程序**链接上方的第一个图表，然后选择或清除复选框中显示的已安装 BizTalk 应用程序的列表。 你也可以使用显示选择所有或应用程序的任何链接。 单击**保存**以显示所选应用程序的信息或单击**取消**放弃所做的更改。 你可以更改应用程序的默认列表上[门户我设置页](../esb-toolkit/portal-my-settings-page.md)。  
  
-   若要更改时间为其门户显示的信息，请更改第一个图表上方的下拉列表中的设置。 你可以选择显示信息之前**小时、 天、 周，** 或**月**。 你可以上更改的默认期限[门户我设置页](../esb-toolkit/portal-my-settings-page.md)。  
  
-   若要打开或关闭自动发布 UDDI 条目，请单击**更改**顶部的链接**注册表**页的部分。 这将打开[注册表设置页](../esb-toolkit/registry-settings-page.md)，其中指定以下：  
  
    -   UDDI 服务器的详细信息门户将使用，包括服务器、 是否已启用自动发布，以及关于是否启用匿名访问的 URI  
  
    -   已启用电子邮件通知的 UDDI 发布，并且设置要用于电子邮件服务器、 电子邮件地址、 邮件主题和消息正文。  
  
    -   已发布的条目你联系人姓名和电子邮件地址。  
  
-   若要查看挂起的 UDDI 注册表请求的列表，请单击顶部的链接**注册表**部分显示的挂起请求数的页面。 这将打开[管理挂起的请求页](../esb-toolkit/manage-pending-requests-page.md)，其中包含以下：  
  
    -   **挂起的注册请求的列表**。 对于每个链接，您可以单击该请求，以查看详细信息、 批准请求，或拒绝请求右侧的图标。 时查看请求，可查看注册表中，注册表服务 （其中你可以编辑） 的详细信息的详细信息和联系人详细信息。  
  
    -   **将其作为列表显示的请求历史记录的链接**。 此列表显示从每个注册请求的值的范围。  
  
-   若要更改排序顺序中列出的错误**错误**部分的页上，单击**日期**或**严重性**选项按钮位于错误的列表。  
  
-   门户将显示在错误**错误**BizTalk 应用程序按分组页的部分。 若要查看的特定应用程序的错误，请单击上面的错误的相关组应用程序的名称的链接。  
  
-   若要查看特定故障的详细信息，请单击任意位置包含在该错误的行中**错误**页的部分。 这将打开[门户错误消息查看器](../esb-toolkit/portal-fault-message-viewer.md)所选的错误。