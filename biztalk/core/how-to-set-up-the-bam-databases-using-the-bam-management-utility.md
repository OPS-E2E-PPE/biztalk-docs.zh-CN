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
ms.openlocfilehash: 6878e6aa3874384bd17f340c62421c432182f637
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001310"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a>如何设置 BAM 数据库使用 BAM 管理实用程序
通常，管理员使用 BizTalk Server 配置实用程序来设置 BAM 数据库。 您可以使用 BAM 管理实用程序 (bm.exe) 作为设置数据库的备选方法。  
  
## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中的过程的前提条件：  
  
-   必须对 BAMPrimaryImport、BAMStarSchema 和 BAMArchive 数据库的宿主 SQL Server 具有管理员权限。  
  
-   若要设置 SQL Notification Services 数据库，必须具有管理员权限，并且是本地管理员组的成员，而且还必须是已配置的任何其他管理员组（如 BTS Admins 组）的成员。  
  
-   必须具有配置数据库所用的、其中包含 XML 数据的 BAM 配置文件。  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a>使用 BAM 管理实用程序设置 BAM 数据库  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。  
  
3. 在命令行提示符下键入以下内容： **bm 设置数据库-ConfigFile:\<配置文件\>**，其中\<*配置文件*\>替换为您的 BAM 配置文件的名称。 按 **Enter**。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)