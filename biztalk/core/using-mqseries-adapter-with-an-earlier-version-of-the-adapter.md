---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 38711ace8fd2c1ea328edc2ba8d4ecf83a320070
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396796"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="c9a20-101">通过早期版本的适配器使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="c9a20-101">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="c9a20-102">不同的 BizTalk Server 版本的 MQSeries 适配器的所有可使用同一远程 WebSphere MQ Server 在 Windows。</span><span class="sxs-lookup"><span data-stu-id="c9a20-102">The different BizTalk Server versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="c9a20-103">这可能是因为与 MQSeries 适配器一起使用的 COM + 应用程序的以下版本可以共存于同一 WebSphere MQSeries 计算机上：</span><span class="sxs-lookup"><span data-stu-id="c9a20-103">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="c9a20-104">**MQSAgent (MQSAgent2) COM + 应用程序**与 MQSeries 适配器 (BizTalk Server 2006) 一起使用</span><span class="sxs-lookup"><span data-stu-id="c9a20-104">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter (BizTalk Server 2006)</span></span> 
  
-   <span data-ttu-id="c9a20-105">**MQSAgent COM + 应用程序**与 MQSeries 适配器 (BizTalk Server 2004) 一起使用</span><span class="sxs-lookup"><span data-stu-id="c9a20-105">**MQSAgent COM+ application** used with the MQSeries Adapter (BizTalk Server 2004)</span></span>  
  
-   <span data-ttu-id="c9a20-106">**MQHelper COM + 应用程序**与 MQSeries 适配器 (BizTalk Server 2002) 一起使用</span><span class="sxs-lookup"><span data-stu-id="c9a20-106">**MQHelper COM+ application** used with the MQSeries Adapter (BizTalk Server 2002)</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="c9a20-107">在配置这些 COM + 应用程序的并行安装，请确保这些 COM + 应用程序配置为使用相同的 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="c9a20-107">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9a20-108">如果在 WebSphere 上未安装早期版本的 BizTalk Server 仅支持通过并行安装 BizTalk Server 2006 版本的 MQSeries 适配器 COM + 应用程序与早期版本的 MQSeries 适配器 COM + 应用程序的MQSeries 计算机。</span><span class="sxs-lookup"><span data-stu-id="c9a20-108">Side-by-side installation of the BizTalk Server 2006 version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="c9a20-109">若要运行的是早期版本的 MQSeries 适配器 COM + 应用程序的 WebSphere MQSeries 计算机上安装 BizTalk Server 2006 版本的 MQSeries 适配器 COM + 应用程序</span><span class="sxs-lookup"><span data-stu-id="c9a20-109">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="c9a20-110">从 BizTalk Server 2006 CD 将依赖文件 MSVCR80.dll 和 msvcp80.dll 复制复制到 WebSphere MQSeries 计算机的 \Platform\BootStrap\ 目录运行 Bootstrap.msi。</span><span class="sxs-lookup"><span data-stu-id="c9a20-110">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the BizTalk Server 2006 CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="c9a20-111">将从 BizTalk Server 2006 cd 的 \msi\program files\ 目录的文件 MQSAgent.dll 复制到 WebSphere MQSeries 计算机中。</span><span class="sxs-lookup"><span data-stu-id="c9a20-111">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the BizTalk Server 2006 CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c9a20-112">此外将文件 MQSTrace.cmd 目录中复制此到 WebSphere MQSeries 计算机如果计划使用 MQSAgent 跟踪实用工具。</span><span class="sxs-lookup"><span data-stu-id="c9a20-112">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="c9a20-113">有关 MQSAgent 跟踪实用工具，请参阅[使用跟踪工具分析 MQSeries 适配器错误](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c9a20-113">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="c9a20-114">手动注册组件 MQSAgent.dll 中通过 WebSphere MQSeries 计算机上运行 regsvr32 mqsagent.dll 以：</span><span class="sxs-lookup"><span data-stu-id="c9a20-114">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c9a20-115">从复制到 MQSAgent.dll 的相同目录中运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c9a20-115">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="c9a20-116">创建一个新 COM + 应用程序为 MQSAgent 组件：</span><span class="sxs-lookup"><span data-stu-id="c9a20-116">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="c9a20-117">右键单击 COM + 应用程序中，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-117">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="c9a20-118">单击**创建一个空应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-118">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="c9a20-119">输入的名称**MQSAgent2**，请保留为默认选项**服务器应用程序**启用，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-119">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="c9a20-120">选择的选项**此用户**，输入相应的帐户信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-120">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c9a20-121">此帐户应具有连接和 put 和/或获取相应的 IBM WebSphere MQ 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="c9a20-121">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="c9a20-122">单击**下一步**在添加**应用程序角色**对话框。</span><span class="sxs-lookup"><span data-stu-id="c9a20-122">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="c9a20-123">单击**下一步**上**向角色添加用户**对话框。</span><span class="sxs-lookup"><span data-stu-id="c9a20-123">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="c9a20-124">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-124">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="c9a20-125">将 MQSAgent.dll 组件添加到 MQSAgent2 COM + 应用程序：</span><span class="sxs-lookup"><span data-stu-id="c9a20-125">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="c9a20-126">单击此项可展开**MQSAgent2** COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9a20-126">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="c9a20-127">右键单击**组件**然后单击**新建**，**组件**以启动 COM + 组件安装向导，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-127">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="c9a20-128">单击**安装新组件**，浏览至文件 MQSAgent.dll，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c9a20-128">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="c9a20-129">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="c9a20-129">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a20-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a20-130">See Also</span></span>  
 [<span data-ttu-id="c9a20-131">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="c9a20-131">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)