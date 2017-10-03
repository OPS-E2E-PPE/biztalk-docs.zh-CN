---
title: "可选配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5e938112b5c49b789b76889a45172d5fc0579a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optional-configurations"></a>可选配置
BizTalk Server 管理包导入后，监视窗格的导航窗格中显示自动发现的对象类型。 对象类型的列表，请参阅[对象管理包发现](../technical-guides/objects-the-management-pack-discovers.md)部分。 你可以修改由发现的对象的默认发现配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包。 使用 Operations Manager 2007 R2/2012年的替代功能更改配置设置。  
  
 对于不自动发现的对象类型，你可以启用自动发现在设置**创作**在操作控制台窗格。  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a>若要使用替代更改自动发现的设置  
  
1.  在创作窗格中，展开**管理包对象**，然后单击**对象发现**。  
  
2.  在 Operations Manager 工具栏上，单击**作用域**，筛选以仅包括 BizTalk Server 对象的详细信息窗格中显示的对象。  
  
3.  在详细信息窗格中，单击你想要更改的设置的对象类型。  
  
4.  在 Operations Manager 工具栏上，单击**重写**，单击**替代对象发现**，然后单击**对于的所有对象类型：** \< *对象类型的名称*>，**对于组，对于特定对象类型：** \<*对象类型的名称*>，或**对于另一种类型的所有对象**.  
  
5.  在**替代属性**对话框中，单击**重写**框**已启用**你想要更改的参数。  
  
6.  下**管理包**，单击**新建**若要创建管理包的未密封的版本，然后单击**确定**。  
  
 更改替代设置后，对象类型将被自动发现，并将显示在下的监视窗格中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 有关设置替代的信息，请参阅[在 Operations Manager 2007 R2/2012年中重写](http://go.microsoft.com/fwlink/?LinkId=86870)(http://go.microsoft.com/fwlink/?LinkId=86870)。