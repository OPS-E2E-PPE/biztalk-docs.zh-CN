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
# <a name="step-3-test-the-migrated-application"></a><span data-ttu-id="a8200-102">步骤 3： 测试已迁移的应用程序</span><span class="sxs-lookup"><span data-stu-id="a8200-102">Step 3: Test the Migrated Application</span></span>
<span data-ttu-id="a8200-103">![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="a8200-103">![Step 3 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="a8200-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="a8200-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="a8200-105">**目标：** 在此步骤中，你将测试已迁移的应用程序发送使用基于 WCF 的平面文件 IDOC [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a8200-105">**Objective:** In this step, you will test the migrated application by sending a flat-file IDOC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8200-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="a8200-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="a8200-107">通过将 BizTalk 业务流程中的逻辑端口映射到在 BizTalk Server 管理控制台中的物理端口来配置 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8200-107">Configure the BizTalk application by mapping the logical ports in the BizTalk orchestration to physical ports in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="a8200-108">配置 BizTalk 应用程序使用 WCF 自定义发送端口进行基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a8200-108">Configure the BizTalk application to use the WCF-custom send port for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
### <a name="to-test-the-migrated-application"></a><span data-ttu-id="a8200-109">测试已迁移应用程序</span><span class="sxs-lookup"><span data-stu-id="a8200-109">To test the migrated application</span></span>  
  
1.  <span data-ttu-id="a8200-110">从 SendIDOC_Migration 文件夹中，将复制 BOMDOC.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="a8200-110">From the SendIDOC_Migration folder, copy the BOMDOC.txt file.</span></span> <span data-ttu-id="a8200-111">这是平面文件 IDOC 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="a8200-111">This is the flat-file IDOC to be sent to the SAP system.</span></span>  
  
2.  <span data-ttu-id="a8200-112">粘贴到映射到文件的文件夹平面文件 IDOC 接收位置。</span><span class="sxs-lookup"><span data-stu-id="a8200-112">Paste the flat-file IDOC to the folder that is mapped to the file receive location.</span></span>  
  
3.  <span data-ttu-id="a8200-113">业务流程使用文件，并将 IDOC 发送到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="a8200-113">The orchestration consumes the file and sends the IDOC to the SAP system.</span></span> <span data-ttu-id="a8200-114">验证事件查看器中是否存在任何错误。</span><span class="sxs-lookup"><span data-stu-id="a8200-114">Verify if there are any errors in the event viewer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8200-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8200-115">See Also</span></span>  
 [<span data-ttu-id="a8200-116">教程 3： 迁移 SAP 发送 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="a8200-116">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)