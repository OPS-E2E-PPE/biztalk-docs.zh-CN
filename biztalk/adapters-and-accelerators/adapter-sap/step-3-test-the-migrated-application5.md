---
title: 步骤 3： 测试已迁移的 Application5 |Microsoft Docs
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
ms.openlocfilehash: 195b150dcbc3edcd1bfe0a18a17c6fe73cb4f50b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009142"
---
# <a name="step-3-test-the-migrated-application"></a>步骤 3： 测试已迁移应用程序
![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，您将测试已迁移应用程序，通过接收使用基于 WCF 的平面文件 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="prerequisites"></a>必要條件  
  
- 通过将 BizTalk 业务流程中的逻辑端口映射到物理端口在 BizTalk Server 管理控制台中配置的 BizTalk 应用程序。  
  
- 配置 BizTalk 应用程序以使用 WCF 自定义接收端口的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>若要测试已迁移应用程序  
  
1.  启动将 SAP GUI，并连接到 SAP 系统的连接 URI 中指定。  
  
2.  运行 SE37，并调用中将 IDOC 发送到外部系统的 SAP 的函数模块。 请确保将发送 IDOC 使用 WCF 自定义接收端口的连接 URI 中指定的同一个程序 ID。  
  
3.  查找在指定为业务流程的一部分的文件位置的入站 IDOC。  
  
## <a name="see-also"></a>请参阅  
 [教程 4：迁移 SAP 接收 IDOC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)