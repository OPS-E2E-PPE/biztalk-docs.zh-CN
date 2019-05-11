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
ms.openlocfilehash: 40677d08d41bfd913427aa18e8f63aef1b6ebaee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384824"
---
# <a name="how-to-list-all-referenced-databases"></a>如何列出所有引用的数据库
管理员使用**get 引用**命令以列出所有已被授予对本地 BAM 主导入数据库的引用其他 BizTalk 服务器上的 BAM 主导入数据库。  
  
### <a name="to-list-all-referenced-databases"></a>若要列出所有引用的数据库  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 在命令行提示符下键入以下内容： **bm.exe get 引用**。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)