---
title: 如何控制结果列表的大小 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- results list [Orchestration Debugger], deleting columns
- results list [Orchestration Debugger], limiting list size
- Orchestration Debugger, results list
- results list [Orchestration Designer]
- results list [Orchestration Debugger], adding columns
ms.assetid: 4d41003f-5ea9-4599-8ec0-737c342ffdbd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80787e4c7dbac57aca9c787943846e924a1a7870
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249733"
---
# <a name="how-to-control-the-size-of-the-results-list"></a>如何控制“结果”列表的大小
上**组中心数据库**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，查询结果窗格中包含太多列的需要进行滚动才能查看它们的信息。 您可以添加或删除窗格中的列，以便只显示所需的信息。 要添加或删除列，请右键单击该查询结果窗格中，然后单击的任何部分**添加/删除列**上下文菜单上。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-add-or-remove-columns-in-the-results-list"></a>添加或删除结果列表中的列  
  
1.  右键单击中的任意单元**查询结果**列表，，然后单击**添加/删除列**上下文菜单上。  
  
    > [!NOTE]
    >  已在结果列表中存在的项目显示在右侧**显示的列**。 在结果列表中不存在的项都显示在下的左边缘**可用列**。  
  
2.  若要添加某一列，选择某一项从**可用列**单击**添加**将该列移到的列表**显示的列**。  
  
3.  若要删除某一列，选择某一项从**显示的列**单击**删除**将该列移到的列表**可用列**。  
  
 您可以使用创建或运行查询时提供的筛选器来控制查询返回的结果数。  
  
## <a name="columns-in-the-query-results-list"></a>“查询结果”列表中的列  
 查询结果显示在发起该查询的视图底部的“查询结果”窗格中。 无法直接访问结果列表。 上下文菜单显示可以对当前活动视图中选定的记录执行的所有操作。 例如，如果记录包含服务实例 ID，则显示与服务有关的操作。 如果记录包含消息 ID，则显示与消息有关的操作。  
  
 由于您可能不需要此完整列表中包含的所有信息，因此可以只选择要查看的列，或者替换所删除的列。 在按时间对结果列表进行排序时，实例可排序到毫秒，即使列表中未显示毫秒也是如此。 如果重新使用保存的查询时，则每次运行查询时，结果中只显示选择的列。  
  
 下表显示了结果列表中显示的完整项目列表。  
  
|||  
|-|-|  
|**服务或消息字段**|**Description**|  
|服务名称|服务实例的名称。|  
|事件类型|服务类型，例如消息传送（报告为管道）、业务流程或传输适配器。|  
|错误说明|出现错误时有关错误的说明。|  
|State|运行查询时的操作状态。|  
|错误代码|出现错误时的错误代码。|  
|解密证书|显示与消息或服务相关的证书信息。|  
|Duration|操作完成所用的时间。|  
|端口名称|实例流中涉及的端口。|  
|签名|消息的数字签名信息。|  
|Size|消息大小（以字节为单位）。|  
|Start Time|时间操作已开始。|  
|结束时间|操作结束时间。|  
|部分计数|消息中的部分数。|  
|聚会|启动操作的参与方的标识符。|  
|URI|发起方的 URI。|  
|TimeStamp|时间操作已开始。|  
|主机|运行服务实例的 BizTalk 主机的名称。|  
|程序集名称|实现服务实例的 .NET 程序集的名称。|  
|程序集版本|相关程序集的版本号。|  
|部署时|将服务实例程序集部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的时间。|  
|活动 ID|标识唯一的服务实例活动（例如，管道/业务流程发送/接收的消息具有相同的 ID）。|  
|服务实例 ID|标识正在运行的服务实例的全局唯一标识符 (GUID)。|  
|消息实例 ID|标识消息实例的全局唯一标识符 (GUID)。|  
|服务 ID|标识服务的全局唯一标识符 (GUID)。|  
|服务类别|类类型（管道或业务流程）。|  
|服务类别 ID|用于标识服务（例如业务流程）的与服务无关的 GUID。|  
|图标|结果行的图标。|  
|适配器|操作中使用的适配器。|