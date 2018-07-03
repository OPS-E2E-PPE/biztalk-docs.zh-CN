---
title: 导入 BizTalk Server 2013 监视管理包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bee2bfe9-4eb0-46d4-8eee-75182202080c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7756a6ca4301f7536a0e4964117f11cb92eb2fcd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993782"
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a>导入 BizTalk Server 2013 监视管理包
有关如何导入管理包时，有关说明，请参阅如何导入中的管理包[Operations Manager 2007 R2/2012年](http://go.microsoft.com/fwlink/?LinkId=142351)(<http://go.microsoft.com/fwlink/?LinkId=142351>)。 之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]导入管理包，请按照这些过程操作以完成初始配置：  
  
### <a name="to-configure-the-management-pack"></a>若要配置的管理包  
  
1.  创建新的管理包在其中存储替代和其他自定义。  
  
2.  若要启用代理程序代理设置，请执行以下步骤：  
  
    1.  打开操作控制台，然后单击管理按钮。  
  
    2.  在管理窗格中，单击**代理管理**。  
  
    3.  双击列表中的代理。  
  
    4.  在安全选项卡上选择**允许此代理充当代理并发现其他计算机上的托管的对象**。  
  
    5.  为每个 BizTalk Server 安装的代理重复步骤 3 至 4。