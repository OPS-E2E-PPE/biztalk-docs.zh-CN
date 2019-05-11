---
title: 管理管道 |Microsoft Docs
description: 若要启用跟踪和管道属性在发送端口或接收位置在 BizTalk Server 中的快速链接
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31e8705a2b7a04689ee4eefa6e3d75d2f063639a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380199"
---
# <a name="managing-pipelines"></a><span data-ttu-id="2480d-103">管理管道</span><span class="sxs-lookup"><span data-stu-id="2480d-103">Managing Pipelines</span></span>

## <a name="overview"></a><span data-ttu-id="2480d-104">概述</span><span class="sxs-lookup"><span data-stu-id="2480d-104">Overview</span></span>
<span data-ttu-id="2480d-105">本部分说明了使用 BizTalk Server 管理控制台来管理 BizTalk 组中的管道。</span><span class="sxs-lookup"><span data-stu-id="2480d-105">This section provides instructions on using the BizTalk Server Administration console to manage the pipelines in a BizTalk group.</span></span> <span data-ttu-id="2480d-106">可以配置跟踪的事件和消息，以及配置管道属性为特定的发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="2480d-106">You can configure tracking for events and messages as well as configure pipeline properties for a specific send port or receive location.</span></span>  
  
 <span data-ttu-id="2480d-107">管道对传入和传出消息，例如将它们从本机格式转换为 XML，加密或解密数据执行属性升级执行操作，依此类推。</span><span class="sxs-lookup"><span data-stu-id="2480d-107">Pipelines perform actions on incoming and outgoing messages, such as transforming them from a native format into XML, encrypting or unencrypting data, performing property promotion, and so on.</span></span>  
  
 <span data-ttu-id="2480d-108">不能单独; 添加到应用程序的管道管道添加到应用程序，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2480d-108">You cannot add a pipeline to an application individually; a pipeline is added to an application as follows:</span></span>  
  
- <span data-ttu-id="2480d-109">当添加包含到应用程序中，管道的 BizTalk 程序集，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2480d-109">When you add a BizTalk assembly containing a pipeline to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="2480d-110">某一.msi 文件导入包含包含管道的 BizTalk 程序集，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2480d-110">When you import an .msi file into an application that includes a BizTalk assembly containing a pipeline, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="2480d-111">当开发人员部署到应用程序的程序集包含在 Visual Studio 中，管道中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2480d-111">When a developer deploys into an application an assembly containing a pipeline from Visual Studio, as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="2480d-112">有关管道的背景信息，请参阅[管道](../core/pipelines.md)。</span><span class="sxs-lookup"><span data-stu-id="2480d-112">For background information about pipelines, see [Pipelines](../core/pipelines.md).</span></span> <span data-ttu-id="2480d-113">有关开发管道的信息，请参阅[管道使用管道设计器创建](../core/creating-pipelines-using-pipeline-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="2480d-113">For information about developing pipelines, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2480d-114">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="2480d-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="2480d-115">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="2480d-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="2480d-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2480d-116">Next steps</span></span>
  
-   [<span data-ttu-id="2480d-117">为管道配置跟踪</span><span class="sxs-lookup"><span data-stu-id="2480d-117">Configure Tracking for a Pipeline</span></span>](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [<span data-ttu-id="2480d-118">为发送端口配置基于实例的管道属性</span><span class="sxs-lookup"><span data-stu-id="2480d-118">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="2480d-119">为接收位置配置基于实例的管道属性</span><span class="sxs-lookup"><span data-stu-id="2480d-119">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)