---
title: 如何启用 Analysis Services 和 BAM 主导入数据库之间加密 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Analysis Services, enabling encryption
- Primary Import database [BAM], SQL Server Analysis Services
- Primary Import database [BAM], enabling encryption
- SQL Server Analysis Services, Primary Import database [BAM]
ms.assetid: 8107c557-e57c-4569-9ff7-abcb7a8e5243
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0de57b8faf73923a8ff5d38c17d693e45afd7b57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349911"
---
# <a name="how-to-enable-encryption-between-analysis-services-and-the-bam-primary-import-database"></a>如何进行 Analysis Services 和 BAM 主导入数据库之间启用加密
不启用默认情况下在安装或升级 BAM 期间进行加密。 若要启用加密，必须为值 1 在 BAM 配置 XML 文件中设置的 UseEncryption 标志。  
  
 此外必须启用 SQL Server Analysis Services 中的加密。 有关启用加密的详细信息，请参阅[使用 Analysis Services 实例保护客户端通信](http://go.microsoft.com/fwlink/?LinkId=190805)(http://go.microsoft.com/fwlink/?LinkId=190805)。  
  
### <a name="to-enable-encryption-between-sql-server-analysis-services-and-the-bam-primary-import-database"></a>若要启用 SQL Server Analysis Services 和 BAM 主导入数据库之间的加密  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
3. 类型**bm 获取配置-FileName:\<输出文件\>**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
4. 按 **Enter**。  
  
5. 打开文件配置文件已在文本编辑器中导出，并将 UseEncryption 属性标志的值更改为 1。  
  
   -   默认设置：\<属性名称 ="UseEncryption"\>0\</Property\>  
  
   -   新的设置：\<属性名称 ="UseEncryption"\>1\</Property\>  
  
6. 通过键入更新 BAM 配置**bm 更新-config-FileName:\<配置文件\>**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="see-also"></a>请参阅  
 [BAM 管理实用工具](../core/bam-management-utility.md)