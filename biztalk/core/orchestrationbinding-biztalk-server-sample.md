---
title: "OrchestrationBinding （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea14c0db-ea83-4bf9-b417-f877b3cb1bf9
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b361968ddb28d629244515281cc02147af533cd0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="orchestrationbinding-biztalk-server-sample"></a><span data-ttu-id="e6368-102">OrchestrationBinding（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e6368-102">OrchestrationBinding (BizTalk Server Sample)</span></span>
<span data-ttu-id="e6368-103">业务流程绑定示例演示使用 [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) 管理对象来配置和管理业务流程。</span><span class="sxs-lookup"><span data-stu-id="e6368-103">The Orchestration Binding sample demonstrates using the [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) administrative objects to configure and manage orchestrations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e6368-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="e6368-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="e6368-105">此示例要求通过运行 setup.bat 位于来部署 HelloWorld 示例\<*示例路径*\>\Orchestrations\HelloWorld 目录。</span><span class="sxs-lookup"><span data-stu-id="e6368-105">This sample requires that the HelloWorld sample be deployed by running setup.bat located in the \<*Samples Path*\>\Orchestrations\HelloWorld directory.</span></span>  
  
-   <span data-ttu-id="e6368-106">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="e6368-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="e6368-107">Windows PowerShell 脚本示例需要 Windows PowerShell 执行策略才能允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="e6368-107">The Windows PowerShell script example requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="e6368-108">有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="e6368-108">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e6368-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="e6368-109">What This Sample Does</span></span>  
 <span data-ttu-id="e6368-110">本示例演示使用 **Microsoft.BizTalk.ExplorerOM** 命名空间中的管理对象来管理业务流程。</span><span class="sxs-lookup"><span data-stu-id="e6368-110">This sample demonstrates using the administrative objects in the **Microsoft.BizTalk.ExplorerOM** namespace to manage orchestrations.</span></span> <span data-ttu-id="e6368-111">本示例演示如何使用 **ExplorerOM** 对象完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="e6368-111">The sample demonstrates the following operations using the **ExplorerOM** objects:</span></span>  
  
-   <span data-ttu-id="e6368-112">使用[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) 类连接到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="e6368-112">Connecting to the BizTalk Management database by using the[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) class.</span></span>  
  
-   <span data-ttu-id="e6368-113">通过更改 **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** 类的 [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) 属性来停止和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="e6368-113">Stopping and starting orchestrations by changing the **Status** property of the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  
  
-   <span data-ttu-id="e6368-114">通过更改 **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** 类的 [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) 属性来登记和取消登记业务流程。</span><span class="sxs-lookup"><span data-stu-id="e6368-114">Enlisting and unenlisting orchestrations by changing the **Status** property of the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  
  
-   <span data-ttu-id="e6368-115">通过使用 **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** 类上的 [Ports](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) 集合来绑定和取消绑定业务流程。</span><span class="sxs-lookup"><span data-stu-id="e6368-115">Binding and unbinding orchestrations by using the **Ports** collection on the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e6368-116">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="e6368-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="e6368-117">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="e6368-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="e6368-118">\<*示例路径*\>\Admin\ExplorerOM\OrchestrationBinding</span><span class="sxs-lookup"><span data-stu-id="e6368-118">\<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding</span></span>  
  
 <span data-ttu-id="e6368-119">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="e6368-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e6368-120">文件</span><span class="sxs-lookup"><span data-stu-id="e6368-120">File(s)</span></span>|<span data-ttu-id="e6368-121">说明</span><span class="sxs-lookup"><span data-stu-id="e6368-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6368-122">OrchestrationBinding.cs</span><span class="sxs-lookup"><span data-stu-id="e6368-122">OrchestrationBinding.cs</span></span>|<span data-ttu-id="e6368-123">本示例中演示的操作所需的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。</span><span class="sxs-lookup"><span data-stu-id="e6368-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="e6368-124">OrchestrationBinding.sln、OrchestrationBinding.csproj、OrchestrationBinding.suo</span><span class="sxs-lookup"><span data-stu-id="e6368-124">OrchestrationBinding.sln, OrchestrationBinding.csproj, OrchestrationBinding.suo</span></span>|<span data-ttu-id="e6368-125">示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="e6368-125">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="e6368-126">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="e6368-126">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="e6368-127">生成示例</span><span class="sxs-lookup"><span data-stu-id="e6368-127">To build this sample</span></span>  
  
1.  <span data-ttu-id="e6368-128">确保您已经完成生成和初始化 HelloWorld 示例的步骤。</span><span class="sxs-lookup"><span data-stu-id="e6368-128">Make sure you have completed the steps for building and initializing the HelloWorld sample.</span></span> <span data-ttu-id="e6368-129">中提供了这些步骤[HelloWorld （BizTalk Server 示例）](../core/helloworld-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="e6368-129">Those steps are provided in [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span>  
  
2.  <span data-ttu-id="e6368-130">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 OrchestrationBinding.sln。</span><span class="sxs-lookup"><span data-stu-id="e6368-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file OrchestrationBinding.sln.</span></span>  
  
3.  <span data-ttu-id="e6368-131">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="e6368-131">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="e6368-132">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="e6368-132">To run this sample</span></span>  
  
1.  <span data-ttu-id="e6368-133">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="e6368-133">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="e6368-134">\<*示例路径*\>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="e6368-134">\<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug</span></span>  
  
2.  <span data-ttu-id="e6368-135">运行文件 OrchestrationBinding.exe 并按照示例提供的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e6368-135">Run the file OrchestrationBinding.exe and follow the directions provided by the sample.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="e6368-136">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="e6368-136">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="e6368-137">以下 Windows PowerShell 脚本可用于演示 **ExplorerOM** 类的相同功能。</span><span class="sxs-lookup"><span data-stu-id="e6368-137">The following Windows PowerShell script can be used to demonstrate the same features of the **ExplorerOM** classes.</span></span>  
  
```  
  
Function RefreshPrompt($oldstatus,$newstatus)  
{  
  Write-Host Orchestration Status should now be `"$oldstatus`"  
  Write-Host Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify   
  
  if ($newstatus)  
  {  
    Write-Host Pressing `<Enter`> now will $newstatus the orchestration using ExplorerOM`.`.`.  
    Read-Host  
    Write-Host "=== Please wait, attempting to $newstatus the orchestration... ===`r`n"  
  }  
  else  
  {  
    write-host `r`n  
  }  
}  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== This sample expects the HelloWorld sample orchestration to be using the ===#  
#=== default name "Biztalk Application 1"                                    ===#  
  
$HelloWorldApp = $Catalog.Applications["Biztalk Application 1"]  
$orch = $HelloWorldApp.orchestrations["Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule"]  
  
#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we need to re-enlist, ===#  
#=== re-bind, or restart the orchestration.                     ===#  
#==================================================================#  
  
$ErrorActionPreference="silentlycontinue"  
trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution...`r`n";$Catalog.DiscardChanges();}  
  
write-host `r`nMake sure the "HelloWorld" sample application is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  
  
#==========================================================#  
#=== Change orchestration state from Started to stopped ===#  
#==========================================================#  
  
RefreshPrompt Started stop  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  
  
#=============================================================#  
#=== Change orchestration state from stopped to unenlisted ===#  
#=============================================================#  
  
RefreshPrompt Stopped unenlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Unenlisted"  
$Catalog.SaveChanges()  
  
#=============================================================#  
#=== Change orchestration state from unenlisted to unbound ===#  
#=============================================================#  
  
RefreshPrompt Unenlisted unbind  
$orch.Ports["SendInvoicePort"].SendPort = $null  
$orch.Ports["ReceivePOPort"].ReceivePort = $null;  
$orch.Host = $null  
$Catalog.SaveChanges()  
  
#==================================================================#  
#=== Change orchestration state from unbound back to unenlisted ===#  
#==================================================================#  
  
RefreshPrompt Unenlisted`(Unbound`) re-bind  
$orch.Ports["SendInvoicePort"].SendPort = $Catalog.SendPorts["HelloWorldSendPort"]  
$orch.Ports["ReceivePOPort"].ReceivePort = $Catalog.ReceivePorts["HelloWorldReceivePort"]  
$orch.Host = $Catalog.Hosts["BizTalkServerApplication"]  
$Catalog.SaveChanges()  
  
#==================================================================#  
#=== Change orchestration state from unenlisted back to stopped ===#  
#==================================================================#  
  
RefreshPrompt Unenlisted enlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  
  
#===============================================================#  
#=== Change orchestration state from stopped back to started ===#  
#===============================================================#  
  
RefreshPrompt Stopped restart  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Started"  
$Catalog.SaveChanges()  
  
RefreshPrompt Started  
  
```  
  
 <span data-ttu-id="e6368-138">下面是运行 Windows PowerShell 脚本的示例输出。</span><span class="sxs-lookup"><span data-stu-id="e6368-138">Here is an example output from running the Windows PowerShell script.</span></span>  
  
```  
PS C:\> .\OrchestrationBind.ps1  
  
Make sure the HelloWorld sample application is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  
  
Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will stop the orchestration using ExplorerOM...  
  
=== Please wait, attempting to stop the orchestration... ===  
  
Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unenlist the orchestration using ExplorerOM...  
  
=== Please wait, attempting to unenlist the orchestration... ===  
  
Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unbind the orchestration using ExplorerOM...  
  
=== Please wait, attempting to unbind the orchestration... ===  
  
Orchestration Status should now be "Unenlisted(Unbound)"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will re-bind the orchestration using ExplorerOM...  
  
=== Please wait, attempting to re-bind the orchestration... ===  
  
Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will enlist the orchestration using ExplorerOM...  
  
=== Please wait, attempting to enlist the orchestration... ===  
  
Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will restart the orchestration using ExplorerOM...  
  
=== Please wait, attempting to restart the orchestration... ===  
  
Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6368-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6368-139">See Also</span></span>  
 <span data-ttu-id="e6368-140">[管理员-ExplorerOM （BizTalk Server 示例文件夹中）](../core/admin-explorerom-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="e6368-140">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="e6368-141">HelloWorld（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e6368-141">HelloWorld (BizTalk Server Sample)</span></span>](../core/helloworld-biztalk-server-sample.md)