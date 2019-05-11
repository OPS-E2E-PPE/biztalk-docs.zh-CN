---
title: 如何使用 BAM 管理实用程序的 BAM 数据库设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01b84fb3e538ee81351cbcfe380d893c5f0cc7b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334098"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a>如何设置 BAM 数据库使用 BAM 管理实用程序
管理员通常使用 BizTalk Server 配置实用工具来设置 BAM 数据库。 可以使用 BAM 管理实用程序 (bm.exe) 作为替代方法，若要设置数据库。  
  
## <a name="prerequisites"></a>先决条件  
 在本主题中执行该过程的先决条件如下：  
  
-   您必须对 BAMPrimaryImport、 BAMStarSchema 和 BAMArchive 数据库的宿主 SQL 服务器上具有管理员权限。  
  
-   若要设置 SQL Notification Services 数据库，您必须具有管理员权限并且是本地管理员组的成员，以及是已配置，如 BTS Admins 组的任何其他管理员组的成员。  
  
-   必须具有包含用于设置数据库的 XML 数据的 BAM 配置文件。  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a>若要设置使用 BAM 管理实用程序的 BAM 数据库  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。  
  
3. 在命令行提示符下键入以下内容： **bm 设置数据库-ConfigFile:\<配置文件\>**，其中\<*配置文件*\>替换为您的 BAM 配置文件的名称。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)