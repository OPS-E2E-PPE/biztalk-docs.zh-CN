---
title: 步骤 3： 测试已迁移应用程序 2 |Microsoft Docs
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
ms.openlocfilehash: cc49906e58e549a8ed9c90446b011dc3b51e0a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017813"
---
# <a name="step-3-test-the-migrated-application"></a>步骤 3： 测试已迁移应用程序
![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，您将测试已迁移应用程序通过发送使用基于 WCF 的平面文件 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="prerequisites"></a>必要條件  
  
- 通过将 BizTalk 业务流程中的逻辑端口映射到物理端口在 BizTalk Server 管理控制台中配置的 BizTalk 应用程序。  
  
- 配置 BizTalk 应用程序要用于 wcf-custom 发送端口基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>若要测试已迁移应用程序  
  
1.  从 SendIDOC_Migration 文件夹中，将复制 BOMDOC.txt 文件。 这是平面文件 IDOC 发送到 SAP 系统。  
  
2.  粘贴到映射到文件的文件夹的平面文件 IDOC 的接收位置。  
  
3.  业务流程使用该文件，并将 IDOC 发送到 SAP 系统。 验证在事件查看器中是否有任何错误。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：迁移 SAP 发送 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)