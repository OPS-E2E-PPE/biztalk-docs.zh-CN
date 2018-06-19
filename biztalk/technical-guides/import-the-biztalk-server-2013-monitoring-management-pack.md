---
title: 导入监视管理包 BizTalk Server 2013 |Microsoft 文档
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
ms.openlocfilehash: 3c6dff55cce17d9b9159a8eca754f91373621929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298629"
---
# <a name="import-the-biztalk-server-2013-monitoring-management-pack"></a>导入监视管理包 BizTalk Server 2013
有关说明有关如何导入管理包，请参阅如何导入管理包中[Operations Manager 2007 R2/2012年](http://go.microsoft.com/fwlink/?LinkId=142351)(http://go.microsoft.com/fwlink/?LinkId=142351)。 后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]导入管理包，请按照这些过程操作以完成初始配置：  
  
### <a name="to-configure-the-management-pack"></a>若要配置管理包  
  
1.  创建新的管理包在其中存储替代和其他自定义。  
  
2.  若要启用代理程序设置，请按照下列步骤：  
  
    1.  打开操作控制台，然后单击管理按钮。  
  
    2.  在管理员窗格中，单击**代理管理**。  
  
    3.  双击列表中的代理。  
  
    4.  在安全选项卡，选择**允许此代理充当代理并发现其他计算机上的托管的对象**。  
  
    5.  为每个 BizTalk 服务器安装的代理重复步骤 3-4。