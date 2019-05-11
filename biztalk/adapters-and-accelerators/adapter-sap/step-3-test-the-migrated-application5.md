---
title: 步骤 3：测试已迁移的 Application5 |Microsoft Docs
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
ms.openlocfilehash: f8754056eeb173fc86201a108e95605074101dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372802"
---
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="69c25-102">步骤 3：测试已迁移应用程序</span><span class="sxs-lookup"><span data-stu-id="69c25-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="69c25-103">![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="69c25-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="69c25-104">**若要完成的时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="69c25-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="69c25-105">**目标：** 在此步骤中，您将测试已迁移应用程序，通过接收使用基于 WCF 的平面文件 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="69c25-105">**Objective:** In this step, you will test the migrated application by receiving a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="69c25-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="69c25-106">Prerequisites</span></span>  
  
- <span data-ttu-id="69c25-107">通过将 BizTalk 业务流程中的逻辑端口映射到物理端口在 BizTalk Server 管理控制台中配置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="69c25-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="69c25-108">配置 BizTalk 应用程序以使用 WCF 自定义接收端口的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="69c25-108">Configure the BizTalk application to use the WCF-Custom receive port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="69c25-109">若要测试已迁移应用程序</span><span class="sxs-lookup"><span data-stu-id="69c25-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="69c25-110">启动将 SAP GUI，并连接到 SAP 系统的连接 URI 中指定。</span><span class="sxs-lookup"><span data-stu-id="69c25-110">Start the SAP GUI, and connect to the SAP system that you specified in the connection URI.</span></span>  
  
2.  <span data-ttu-id="69c25-111">运行 SE37，并调用中将 IDOC 发送到外部系统的 SAP 的函数模块。</span><span class="sxs-lookup"><span data-stu-id="69c25-111">Run SE37, and invoke a function module in SAP that sends an IDOC to an external system.</span></span> <span data-ttu-id="69c25-112">请确保将发送 IDOC 使用 WCF 自定义接收端口的连接 URI 中指定的同一个程序 ID。</span><span class="sxs-lookup"><span data-stu-id="69c25-112">Make sure you send the IDOC using the same program ID that is specified in the connection URI for the WCF-Custom receive port.</span></span>  
  
3.  <span data-ttu-id="69c25-113">查找在指定为业务流程的一部分的文件位置的入站 IDOC。</span><span class="sxs-lookup"><span data-stu-id="69c25-113">Look for the inbound IDOC at the file location specified as part of the orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c25-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="69c25-114">See Also</span></span>  
 [<span data-ttu-id="69c25-115">教程 4：迁移 SAP 接收 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="69c25-115">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)