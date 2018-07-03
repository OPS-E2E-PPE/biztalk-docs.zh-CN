---
title: 如何列出所有引用的数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76a953933d72803b718353f7d0456317585b1458
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968470"
---
# <a name="how-to-list-all-referenced-databases"></a>如何列出所有引用的数据库
管理员使用**get 引用**命令以列出所有已被授予对本地 BAM 主导入数据库的引用其他 BizTalk 服务器上的 BAM 主导入数据库。  
  
### <a name="to-list-all-referenced-databases"></a>列出所有引用的数据库  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3. 在命令行提示符下键入以下内容： **bm.exe get 引用**。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)