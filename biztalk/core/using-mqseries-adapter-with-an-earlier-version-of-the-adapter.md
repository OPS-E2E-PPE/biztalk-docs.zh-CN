---
title: "使用早期版本的适配器 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: MQSeries adapters, compatibility
ms.assetid: 278a13ff-8e46-4af4-a76e-b6d4aad5b768
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba635b9bc4569f17418fc925c54c64d0fdc67461
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="1a1b4-102">MQSeries 适配器使用早期版本的适配器</span><span class="sxs-lookup"><span data-stu-id="1a1b4-102">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="1a1b4-103">[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]， [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]，和[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]MQSeries 适配器版本可以与相同的远程 WebSphere MQ 服务器在 Windows 上的所有工作。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-103">The [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)], [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], and [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="1a1b4-104">这是由于与 MQSeries 适配器一起使用的以下版本的 COM+ 应用程序可以同时存在于同一 WebSphere MQSeries 计算机上：</span><span class="sxs-lookup"><span data-stu-id="1a1b4-104">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="1a1b4-105">**MQSAgent (MQSAgent2) COM + 应用程序**与 MQSeries 适配器[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-105">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)].</span></span>  
  
-   <span data-ttu-id="1a1b4-106">**MQSAgent COM + 应用程序**与 MQSeries 适配器[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-106">**MQSAgent COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)].</span></span>  
  
-   <span data-ttu-id="1a1b4-107">**MQHelper COM + 应用程序**与 MQSeries 适配器[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-107">**MQHelper COM+ application** used with the MQSeries Adapter for [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a1b4-108">在配置这些 COM+ 应用程序的并行安装时，请确保这些 COM+ 应用程序均未配置为使用相同的 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-108">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1a1b4-109">通过并行安装[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]支持仅使用 MQSeries 适配器 COM + 应用程序的较早版本 MQSeries 适配器 COM + 应用程序的版本，如果 WebSphere MQSeries 上未安装 BizTalk Server 的早期版本计算机。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-109">Side-by-side installation of the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="1a1b4-110">将 BizTalk Server 2006 版本的 MQSeries 适配器 COM+ 应用程序安装在运行早期版本的 MQSeries 适配器 COM+ 应用程序的 WebSphere MQSeries 计算机上</span><span class="sxs-lookup"><span data-stu-id="1a1b4-110">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="1a1b4-111">从的 \Platform\BootStrap\ 目录中运行 Bootstrap.msi [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD 来复制依赖项文件到 WebSphere MQSeries 计算机 MSVCR80.dll 和 MSVCP80.dll。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-111">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="1a1b4-112">在将文件复制 MQSAgent.dll 从 \Msi\Program Files\ 目录[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]键入 cd 转到 WebSphere MQSeries 计算机。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-112">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a1b4-113">如果您计划使用 MQSAgent 跟踪实用工具，请从此目录将文件 MQSTrace.cmd 也复制到 WebSphere MQSeries 计算机中。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-113">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="1a1b4-114">跟踪实用工具 MQSAgent 有关详细信息请参阅[分析 MQSeries 适配器跟踪工具错误](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-114">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="1a1b4-115">请通过在 WebSphere MQSeries 计算机上运行 regsvr32 mqsagent.dll 以手动方式注册 MQSAgent.dll 中的组件。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-115">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="1a1b4-116">从 MQSAgent.dll 所复制到的目标目录运行此命令。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-116">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="1a1b4-117">为 MQSAgent 组件创建新的 COM+ 应用程序：</span><span class="sxs-lookup"><span data-stu-id="1a1b4-117">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="1a1b4-118">右键单击 COM + 应用程序，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-118">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="1a1b4-119">单击**创建空的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-119">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="1a1b4-120">输入的名称**MQSAgent2**，保留默认选项为**服务器应用程序**启用和单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-120">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="1a1b4-121">选择的选项**此用户**，输入合适的帐户信息，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-121">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1a1b4-122">该帐户应该在相应的 IBM WebSphere MQ 队列中拥有 connect 及 put 和/或 get 权限。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-122">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="1a1b4-123">单击**下一步**在添加**应用程序角色**对话框。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-123">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="1a1b4-124">单击**下一步**上**向角色添加用户**对话框。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-124">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="1a1b4-125">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-125">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="1a1b4-126">将 MQSAgent.dll 组件添加到 MQSAgent2 COM+ 应用程序：</span><span class="sxs-lookup"><span data-stu-id="1a1b4-126">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="1a1b4-127">单击以展开**MQSAgent2** COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-127">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="1a1b4-128">右键单击**组件**单击**新建**，**组件**启动 COM + 组件安装向导，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-128">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="1a1b4-129">单击**安装新组件**，浏览到文件 MQSAgent.dll，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-129">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="1a1b4-130">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="1a1b4-130">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a1b4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a1b4-131">See Also</span></span>  
 [<span data-ttu-id="1a1b4-132">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="1a1b4-132">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)