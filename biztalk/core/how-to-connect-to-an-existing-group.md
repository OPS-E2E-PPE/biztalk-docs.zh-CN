---
title: 如何连接到现有组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e29b57f39ab1cb86e34a9e744063ff248d12ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994350"
---
# <a name="how-to-connect-to-an-existing-group"></a>如何连接到现有组
只要企业中的一个或多个 BizTalk Server 组位于同一域或可信域中的计算机上，你就可以在企业中任何计算机上使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台远程管理这些组。  
  
 BizTalk Server 管理控制台中的 BizTalk Server 管理节点是所有的 BizTalk 组的最高级别的节点，将现有的 BizTalk Server 组添加到 BizTalk Server 管理控制台时，使用的级别。 在添加组时，必须指定要连接到的现有服务器和 BizTalk 管理数据库。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行此步骤，则必须以 BizTalk Server Operators 组成员或 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-connect-to-an-existing-group"></a>连接到现有组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，右键单击**BizTalk Server 管理**，然后单击**连接到现有组**。  
  
3. 在中**连接到现有 BizTalk Server 配置数据库**对话框中**SQL Server 名称**下拉列表框中，选择承载 BizTalk 的 Microsoft SQL Server 实例的名称管理数据库 （也称为配置数据库）。 在选择 SQL Server 的实例后，BizTalk Server 将自动尝试检测该计算机上的 BizTalk Server 数据库。  
  
4. 在中**数据库名称**下拉列表框中，选择 BizTalk Server 管理数据库 (**BizTalkMgmtDb**) 到想要连接，然后单击**确定**。  
  
    在 BizTalk Server 管理控制台将 BizTalk Server 组添加到控制台树中。  
  
   > [!NOTE]
   >  如果 BizTalk Server 管理数据库存储在 SQL Server 群集上，且该群集正在进行故障转移，则在尝试连接到管理数据库时，可能会出现类似下面的错误：  
   >   
   >  无法加载组 [\<servername\>:\<管理数据库\>] 数据提供程序。  
   >   
   >  And  
   >   
   >  其他信息：  
   >   
   >  找不到 WMI 类的实例。 (WinMgmt)  
   >   
   >  出现这种错误的原因是，BizTalk 数据库在进行故障转移时不可用。 解决此问题，请在 SQL Server 的群集实例之前等待处于联机状态之前尝试使用在 BizTalk Server 管理控制台连接到它。  
  
## <a name="see-also"></a>请参阅  
 [管理组](../core/managing-groups.md)   
 [BizTalk 组](../core/biztalk-groups.md)