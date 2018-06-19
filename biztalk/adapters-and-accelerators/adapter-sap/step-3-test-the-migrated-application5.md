---
title: 步骤 3： 测试迁移的 Application5 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Receive IDOC)
- migration
ms.assetid: 3ad15069-1556-4c0a-8bfd-86704d40c586
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5e49968e4b0b463b1665d0752689a14039c2da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217245"
---
# <a name="step-3-test-the-migrated-application"></a>步骤 3： 测试已迁移的应用程序
![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，你将测试已迁移的应用程序接收使用基于 WCF 的平面文件 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="prerequisites"></a>先决条件  
  
-   通过将 BizTalk 业务流程中的逻辑端口映射到在 BizTalk Server 管理控制台中的物理端口来配置 BizTalk 应用程序。  
  
-   配置 BizTalk 应用程序以使用 WCF 自定义接收端口的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>测试已迁移应用程序  
  
1.  启动 SAP GUI，并连接到 SAP 系统连接 URI 中指定。  
  
2.  运行 SE37，并调用中将 IDOC 发送到外部系统的 SAP 的函数模块。 请确保你将 IDOC 发送使用 WCF 自定义接收端口连接 URI 中指定的同一程序 ID。  
  
3.  对于入站 IDOC 看业务流程的一部分指定的文件位置。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 迁移 SAP 接收 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)