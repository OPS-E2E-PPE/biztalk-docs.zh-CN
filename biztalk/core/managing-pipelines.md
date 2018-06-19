---
title: 管理管道 |Microsoft 文档
description: 若要启用跟踪和发送端口上的管道属性或在 BizTalk Server 接收位置的快速链接
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
ms.openlocfilehash: 0edfbdd97e134abc6f153acf136ff62a979f8b0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262533"
---
# <a name="managing-pipelines"></a><span data-ttu-id="c8031-103">管理管道</span><span class="sxs-lookup"><span data-stu-id="c8031-103">Managing Pipelines</span></span>

## <a name="overview"></a><span data-ttu-id="c8031-104">概述</span><span class="sxs-lookup"><span data-stu-id="c8031-104">Overview</span></span>
<span data-ttu-id="c8031-105">本部分说明如何使用 BizTalk Server 管理控制台来管理 BizTalk 组中的管道。</span><span class="sxs-lookup"><span data-stu-id="c8031-105">This section provides instructions on using the BizTalk Server Administration console to manage the pipelines in a BizTalk group.</span></span> <span data-ttu-id="c8031-106">您既可为事件和消息配置跟踪，也可为特定发送端口或接收位置配置管道属性。</span><span class="sxs-lookup"><span data-stu-id="c8031-106">You can configure tracking for events and messages as well as configure pipeline properties for a specific send port or receive location.</span></span>  
  
 <span data-ttu-id="c8031-107">管道对传入消息和传出消息执行操作，例如将其从本机格式转换为 XML 格式、加密或解密数据、执行属性升级等等。</span><span class="sxs-lookup"><span data-stu-id="c8031-107">Pipelines perform actions on incoming and outgoing messages, such as transforming them from a native format into XML, encrypting or unencrypting data, performing property promotion, and so on.</span></span>  
  
 <span data-ttu-id="c8031-108">不能向应用程序单独添加管道，而应按照以下方式向应用程序添加管道：</span><span class="sxs-lookup"><span data-stu-id="c8031-108">You cannot add a pipeline to an application individually; a pipeline is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="c8031-109">当你添加 BizTalk 程序集包含应用程序，管道中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c8031-109">When you add a BizTalk assembly containing a pipeline to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="c8031-110">当你导入的应用程序中所述包括 BizTalk 程序集包含管道，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c8031-110">When you import an .msi file into an application that includes a BizTalk assembly containing a pipeline, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="c8031-111">当开发人员将部署到应用程序包含从 Visual Studio 中，管道的程序集中所述[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c8031-111">When a developer deploys into an application an assembly containing a pipeline from Visual Studio, as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="c8031-112">有关管道的背景信息，请参阅[管道](../core/pipelines.md)。</span><span class="sxs-lookup"><span data-stu-id="c8031-112">For background information about pipelines, see [Pipelines](../core/pipelines.md).</span></span> <span data-ttu-id="c8031-113">有关开发管道的信息，请参阅[创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="c8031-113">For information about developing pipelines, see [Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8031-114">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="c8031-114">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="c8031-115">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c8031-115">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c8031-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8031-116">Next steps</span></span>
  
-   [<span data-ttu-id="c8031-117">配置为管道的跟踪</span><span class="sxs-lookup"><span data-stu-id="c8031-117">Configure Tracking for a Pipeline</span></span>](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [<span data-ttu-id="c8031-118">配置每个实例管道发送端口属性</span><span class="sxs-lookup"><span data-stu-id="c8031-118">Configure Per-Instance Pipeline Properties for a Send Port</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [<span data-ttu-id="c8031-119">配置每个实例的管道属性接收位置</span><span class="sxs-lookup"><span data-stu-id="c8031-119">Configure Per-instance Pipeline Properties for a Receive Location</span></span>](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)