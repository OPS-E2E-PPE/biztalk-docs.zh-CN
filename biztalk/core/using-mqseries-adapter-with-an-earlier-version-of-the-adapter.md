---
redirect_url: /biztalk/core/mqseries-adapter-deployment-options
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2aa74be2d86bcb8f32661fdcf06727eb6391861d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710704"
---
# <a name="using-mqseries-adapter-with-an-earlier-version-of-the-adapter"></a><span data-ttu-id="c5163-101">MQSeries 适配器使用早期版本的适配器</span><span class="sxs-lookup"><span data-stu-id="c5163-101">Using MQSeries Adapter with an Earlier Version of the Adapter</span></span>
<span data-ttu-id="c5163-102">MQSeries 适配器的不同 BizTalk Server 版本可以所有使用同一个远程 WebSphere MQ 服务器上 Windows。</span><span class="sxs-lookup"><span data-stu-id="c5163-102">The different BizTalk Server versions of the MQSeries adapter can all work with the same remote WebSphere MQ Server on Windows.</span></span> <span data-ttu-id="c5163-103">这是由于与 MQSeries 适配器一起使用的以下版本的 COM+ 应用程序可以同时存在于同一 WebSphere MQSeries 计算机上：</span><span class="sxs-lookup"><span data-stu-id="c5163-103">This is possible because the following versions of the COM+ applications used with the MQSeries adapter can coexist on the same WebSphere MQSeries computer:</span></span>  
  
-   <span data-ttu-id="c5163-104">**MQSAgent (MQSAgent2) COM + 应用程序**用于 MQSeries 适配器 (BizTalk Server 2006)</span><span class="sxs-lookup"><span data-stu-id="c5163-104">**MQSAgent (MQSAgent2) COM+ application** used with the MQSeries Adapter (BizTalk Server 2006)</span></span> 
  
-   <span data-ttu-id="c5163-105">**MQSAgent COM + 应用程序**用于 MQSeries 适配器 （BizTalk Server 2004 年）</span><span class="sxs-lookup"><span data-stu-id="c5163-105">**MQSAgent COM+ application** used with the MQSeries Adapter (BizTalk Server 2004)</span></span>  
  
-   <span data-ttu-id="c5163-106">**MQHelper COM + 应用程序**用于 MQSeries 适配器 (BizTalk Server 2002)</span><span class="sxs-lookup"><span data-stu-id="c5163-106">**MQHelper COM+ application** used with the MQSeries Adapter (BizTalk Server 2002)</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="c5163-107">在配置这些 COM+ 应用程序的并行安装时，请确保这些 COM+ 应用程序均未配置为使用相同的 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="c5163-107">When configuring a side-by-side installation of these COM+ applications, ensure that none of these COM+ applications are configured to use the same MQSeries queues.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c5163-108">如果上 WebSphere 未安装 BizTalk Server 的早期版本，则仅支持通过并行安装的 MQSeries 适配器 COM + 应用程序使用 MQSeries 适配器 COM + 应用程序的较早版本的 BizTalk Server 2006 版本MQSeries 计算机。</span><span class="sxs-lookup"><span data-stu-id="c5163-108">Side-by-side installation of the BizTalk Server 2006 version of the MQSeries Adapter COM+ application with an earlier version of the MQSeries Adapter COM+ application is only supported if an earlier version of BizTalk Server is not installed on the WebSphere MQSeries computer.</span></span>  
  
### <a name="to-install-the-biztalk-server-2006-version-of-the-mqseries-adapter-com-application-on-a-websphere-mqseries-computer-that-is-running-an-earlier-version-of-the-mqseries-adapter-com-application"></a><span data-ttu-id="c5163-109">将 BizTalk Server 2006 版本的 MQSeries 适配器 COM+ 应用程序安装在运行早期版本的 MQSeries 适配器 COM+ 应用程序的 WebSphere MQSeries 计算机上</span><span class="sxs-lookup"><span data-stu-id="c5163-109">To install the BizTalk Server 2006 version of the MQSeries Adapter COM+ application on a WebSphere MQSeries computer that is running an earlier version of the MQSeries Adapter COM+ application</span></span>  
  
1.  <span data-ttu-id="c5163-110">从 BizTalk Server 2006 CD 来将 MSVCR80.dll 和 MSVCP80.dll 的依赖文件复制到 WebSphere MQSeries 计算机的 \Platform\BootStrap\ 目录中运行 Bootstrap.msi。</span><span class="sxs-lookup"><span data-stu-id="c5163-110">Run the Bootstrap.msi from the \Platform\BootStrap\ directory of the BizTalk Server 2006 CD to copy the dependency files MSVCR80.dll and MSVCP80.dll to the WebSphere MQSeries computer.</span></span>  
  
2.  <span data-ttu-id="c5163-111">将文件 MQSAgent.dll 从 BizTalk Server 2006 CD 上的 \Msi\Program Files\ 目录复制到 WebSphere MQSeries 计算机。</span><span class="sxs-lookup"><span data-stu-id="c5163-111">Copy the file MQSAgent.dll from the \Msi\Program Files\ directory on the BizTalk Server 2006 CD to the WebSphere MQSeries computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c5163-112">如果您计划使用 MQSAgent 跟踪实用工具，请从此目录将文件 MQSTrace.cmd 也复制到 WebSphere MQSeries 计算机中。</span><span class="sxs-lookup"><span data-stu-id="c5163-112">Also copy the file MQSTrace.cmd from this directory to the WebSphere MQSeries computer if you plan on using the MQSAgent tracing utility.</span></span> <span data-ttu-id="c5163-113">跟踪实用工具 MQSAgent 有关详细信息请参阅[分析 MQSeries 适配器跟踪工具错误](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c5163-113">For more information about the MQSAgent tracing utility see [Analyzing MQSeries Adapter Errors with the Trace Tools](../core/analyzing-mqseries-adapter-errors-with-the-trace-tools.md).</span></span>  
  
3.  <span data-ttu-id="c5163-114">请通过在 WebSphere MQSeries 计算机上运行 regsvr32 mqsagent.dll 以手动方式注册 MQSAgent.dll 中的组件。</span><span class="sxs-lookup"><span data-stu-id="c5163-114">Manually register the components in MQSAgent.dll by running regsvr32 mqsagent.dll on the WebSphere MQSeries computer:</span></span>  
  
    ```  
    regsvr32 MQSAgent.dll  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c5163-115">从 MQSAgent.dll 所复制到的目标目录运行此命令。</span><span class="sxs-lookup"><span data-stu-id="c5163-115">Run this command from the same directory that you copied MQSAgent.dll to.</span></span>  
  
4.  <span data-ttu-id="c5163-116">为 MQSAgent 组件创建新的 COM+ 应用程序：</span><span class="sxs-lookup"><span data-stu-id="c5163-116">Create a new COM+ application for the MQSAgent components:</span></span>  
  
    -   <span data-ttu-id="c5163-117">右键单击 COM + 应用程序，单击 **新建**, ，**应用程序** 以显示 **COM + 应用程序安装向导** 单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5163-117">Right-click COM+ Applications, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="c5163-118">单击 **创建空的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="c5163-118">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="c5163-119">输入的名称 **MQSAgent2**, ，保留默认选项为 **服务器应用程序** 启用和单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5163-119">Enter the name **MQSAgent2**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="c5163-120">选择的选项 **此用户**, ，输入合适的帐户信息，请单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5163-120">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c5163-121">该帐户应该在相应的 IBM WebSphere MQ 队列中拥有 connect 及 put 和/或 get 权限。</span><span class="sxs-lookup"><span data-stu-id="c5163-121">This account should have connect and put and/or get permissions on the appropriate IBM WebSphere MQ queues.</span></span>  
  
    -   <span data-ttu-id="c5163-122">单击 **下一步** 在添加 **应用程序角色** 对话框。</span><span class="sxs-lookup"><span data-stu-id="c5163-122">Click **Next** on the Add **Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="c5163-123">单击 **下一步** 上 **向角色添加用户** 对话框。</span><span class="sxs-lookup"><span data-stu-id="c5163-123">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="c5163-124">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="c5163-124">Click **Finish**.</span></span>  
  
5.  <span data-ttu-id="c5163-125">将 MQSAgent.dll 组件添加到 MQSAgent2 COM+ 应用程序：</span><span class="sxs-lookup"><span data-stu-id="c5163-125">Add the MQSAgent.dll components to the MQSAgent2 COM+ application:</span></span>  
  
    -   <span data-ttu-id="c5163-126">单击以展开 **MQSAgent2** COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5163-126">Click to expand the **MQSAgent2** COM+ Application.</span></span>  
  
    -   <span data-ttu-id="c5163-127">右键单击 **组件** 单击 **新建**, ，**组件** 启动 COM + 组件安装向导，然后单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="c5163-127">Right-click **Components** and click **New**, **Component** to launch the COM+ Component Install Wizard and then click **Next**.</span></span>  
  
    -   <span data-ttu-id="c5163-128">单击 **安装新组件**, ，浏览到文件 MQSAgent.dll，然后单击 **打开**。</span><span class="sxs-lookup"><span data-stu-id="c5163-128">Click **Install New Components**, browse to the file MQSAgent.dll and then click **Open**.</span></span>  
  
    -   <span data-ttu-id="c5163-129">单击“下一步” ，然后单击“完成” 。</span><span class="sxs-lookup"><span data-stu-id="c5163-129">Click **Next**, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5163-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5163-130">See Also</span></span>  
 [<span data-ttu-id="c5163-131">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="c5163-131">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)