---
title: 从暖备份中还原生产 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e590b4eccb6ee946a915ff1f3a0265bbfe977e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302085"
---
# <a name="restoring-production-from-a-warm-backup"></a>从暖备份中还原生产
如果源系统开始变得不可靠，则可以从目标到源中还原数据库。 执行以下过程将从目标的数据库还原到源。  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a>若要还原到源从目标数据库，请按照下列步骤  
  
1.  禁用源 （生产） 上的所有备份作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
2.  等待所有还原作业来在目标灾难恢复 (DR) 上完成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
3.  禁用目标 (DR) 上的所有还原作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
4.  还原与 STOPATMARK 目标 (DR) 上的所有数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
5.  停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所有 BizTalk 服务器上的服务。  
  
6.  删除所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-相关数据库上的源 （生产）[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
7.  备份 （完整） 的所有数据库上的目标 (DR)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
8.  还原 （完整） 所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份在步骤 7 中的源 （生产） 到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
9. 重新启动所有 BizTalk 服务器包括主密钥服务器。  
  
10. 删除所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-相关目标 (DR) 上的数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
11. 启用源上的备份作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
12. 启用目标 (DR) 上的还原作业[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例。  
  
## <a name="see-also"></a>另请参阅  
 [有关备份和 Restore2 的高级的信息](../technical-guides/advanced-information-about-backup-and-restore2.md)