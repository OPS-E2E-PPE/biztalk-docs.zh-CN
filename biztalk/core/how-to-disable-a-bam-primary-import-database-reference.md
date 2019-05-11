---
title: 如何禁用 BAM 主导入数据库引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a2cf04865e4806882d3377f03b3c44e387e12f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338131"
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a>如何禁用 BAM 主导入数据库引用
管理员使用**禁用引用**命令，以禁用对指定 BAM 主导入数据库的引用。  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a>若要禁用对 BAM 主导入数据库的引用  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 在命令行提示符下键入以下内容： **bm 禁用引用-TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<server\> ][-数据库：\<数据库\>]**，其中**\<**<em>目标服务器</em>**\>** 替换为在其通过将指定的目标 BAM 主导入数据库的 SQL server 的名称\<*目标数据库*\>驻留。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)