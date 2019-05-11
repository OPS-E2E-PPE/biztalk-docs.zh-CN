---
title: 如何更新 BAM 配置使用 BAM 管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f497fa345dd643429dac7c48d43e04646fd81f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333700"
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>如何更新 BAM 配置使用 BAM 管理实用程序
管理员可以使用 BAM 管理实用程序来更新现有 BAM 安装。  
  
## <a name="prerequisites"></a>先决条件  
 正在更新对 BAM 数据库，必须具有管理员权限。  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>若要更新 BAM 配置使用 BAM 管理实用程序  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 在命令行提示符下键入以下内容： **bm 更新-config-FileName:\<配置文件\>**，其中\<*配置文件*\>是替换为您的 BAM 配置文件的名称。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)