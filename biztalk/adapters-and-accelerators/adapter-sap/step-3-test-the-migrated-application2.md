---
title: 步骤 3： 测试迁移的 Application2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Send IDOC)
- migration
ms.assetid: 8dc0d127-71ce-4668-a3bf-c893a8f6848d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dbf6154337dc9daf5dcfe75b3f5b7299ae843ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216461"
---
# <a name="step-3-test-the-migrated-application"></a>步骤 3： 测试已迁移的应用程序
![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，你将测试已迁移的应用程序发送使用基于 WCF 的平面文件 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="prerequisites"></a>先决条件  
  
-   通过将 BizTalk 业务流程中的逻辑端口映射到在 BizTalk Server 管理控制台中的物理端口来配置 BizTalk 应用程序。  
  
-   配置 BizTalk 应用程序使用 WCF 自定义发送端口进行基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>测试已迁移应用程序  
  
1.  从 SendIDOC_Migration 文件夹中，将复制 BOMDOC.txt 文件。 这是平面文件 IDOC 发送到 SAP 系统。  
  
2.  粘贴到映射到文件的文件夹平面文件 IDOC 接收位置。  
  
3.  业务流程使用文件，并将 IDOC 发送到 SAP 系统。 验证事件查看器中是否存在任何错误。  
  
## <a name="see-also"></a>另请参阅  
 [教程 3： 迁移 SAP 发送 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)