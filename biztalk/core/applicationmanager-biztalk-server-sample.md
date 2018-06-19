---
title: ApplicationManager （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ebe7a8-a0ca-4d2a-bf40-ec6421ba5a95
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 374fc67f0a4b750aa1f797d57778f68347383736
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965579"
---
# <a name="applicationmanager-biztalk-server-sample"></a><span data-ttu-id="ed6b7-102">ApplicationManager（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="ed6b7-102">ApplicationManager (BizTalk Server Sample)</span></span>
<span data-ttu-id="ed6b7-103">ApplicationManager 示例演示如何使用管理对象启动或停止 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-103">The ApplicationManager sample demonstrates how to start or stop a  BizTalk application by using the administration objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ed6b7-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="ed6b7-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="ed6b7-105">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="ed6b7-106">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="ed6b7-107">有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-107">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ed6b7-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="ed6b7-108">What This Sample Does</span></span>  
 <span data-ttu-id="ed6b7-109">此示例演示如何使用**BtsCatalogExplorer**和**应用程序**类从**Microsoft.BizTalk.ExplorerOM**启动和停止已部署的命名空间 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-109">This sample demonstrates using the **BtsCatalogExplorer** and **Application** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to start and stop a deployed  BizTalk application.</span></span> <span data-ttu-id="ed6b7-110">本示例是使用 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 编写的。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="ed6b7-111">本主题中还包含 Windows PowerShell 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="ed6b7-112">本示例将演示以下操作：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-112">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="ed6b7-113">使用连接到 BizTalk 管理数据库**BtsCatalogExplorer**类。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
-   <span data-ttu-id="ed6b7-114">查找中的应用程序实例**BtsCatalogExplorer**基于应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-114">Finding an application instance from  **BtsCatalogExplorer** based on application name.</span></span>  
  
-   <span data-ttu-id="ed6b7-115">提交应用程序的启动和停止命令。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-115">Submitting a start or stop command for the application.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ed6b7-116">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="ed6b7-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="ed6b7-117">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="ed6b7-118">\<*示例路径*\>\Admin\ExplorerOM\ApplicationManager</span><span class="sxs-lookup"><span data-stu-id="ed6b7-118">\<*Samples Path*\>\Admin\ExplorerOM\ApplicationManager</span></span>  
  
 <span data-ttu-id="ed6b7-119">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ed6b7-120">文件</span><span class="sxs-lookup"><span data-stu-id="ed6b7-120">File(s)</span></span>|<span data-ttu-id="ed6b7-121">Description</span><span class="sxs-lookup"><span data-stu-id="ed6b7-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed6b7-122">Program.cs</span><span class="sxs-lookup"><span data-stu-id="ed6b7-122">Program.cs</span></span>|<span data-ttu-id="ed6b7-123">本示例中演示的操作所需的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="ed6b7-124">ApplicationManager.sln、ApplicationManager.csproj、ApplicationManager.suo</span><span class="sxs-lookup"><span data-stu-id="ed6b7-124">ApplicationManager.sln,ApplicationManager.csproj,ApplicationManager.suo</span></span>|<span data-ttu-id="ed6b7-125">示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-125">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="ed6b7-126">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="ed6b7-126">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="ed6b7-127">生成示例</span><span class="sxs-lookup"><span data-stu-id="ed6b7-127">To build this sample</span></span>  
  
1.  <span data-ttu-id="ed6b7-128">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 ApplicationManager.sln。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ApplicationManager.sln.</span></span>  
  
2.  <span data-ttu-id="ed6b7-129">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-129">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="ed6b7-130">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="ed6b7-130">To run this sample</span></span>  
  
1.  <span data-ttu-id="ed6b7-131">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-131">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="ed6b7-132">\<*示例路径*\>\Admin\ExplorerOM\ApplicationManager\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="ed6b7-132">\<*Samples Path*\>\Admin\ExplorerOM\ApplicationManager\bin\Debug</span></span>  
  
2.  <span data-ttu-id="ed6b7-133">运行文件 ApplicationManager.exe 提供以下两个有序命令行参数：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-133">Run the file ApplicationManager.exe providing the following two ordered command-line arguments:</span></span>  
  
    -   <span data-ttu-id="ed6b7-134">**\<开始 &#124; 停止\>** 第一个参数是要部署的应用程序执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-134">**\<start&#124;stop\>** First argument is the operation to be performed on the deployed application.</span></span>  
  
    -   <span data-ttu-id="ed6b7-135">**\<ApplicationName\>** 第二个参数是部署的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-135">**\<ApplicationName\>** Second argument is the name of the deployed application.</span></span>  
  
     <span data-ttu-id="ed6b7-136">例如：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-136">For example:</span></span>  
  
    ```  
    ApplicationManager.exe stop MyBizTalkApp  
    ```  
  
     <span data-ttu-id="ed6b7-137">命令行参数不足时运行示例将显示使用语法。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-137">Running the sample with insufficient command-line parameters displays the usage syntax.</span></span> <span data-ttu-id="ed6b7-138">例如：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-138">For example:</span></span>  
  
    ```  
    Usage:  
  
    ApplicationManager <start|stop> <Application Name>  
  
     Where:  
      <Application Name> = The name of the application that needs to be changed  
  
    Example: ApplicationManager start Application1  
    ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="ed6b7-139">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="ed6b7-139">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="ed6b7-140">以下 Windows PowerShell 脚本片段可以用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== Loop through applications in the catalog trying to find a name match ===#  
  
foreach($app in $Catalog.Applications)  
{  
    if ($($app.Name) -ieq $args[1])  
    {  
  
        #=== The first command-line argument should be "start" or "stop" ===#  
  
        if ($args[0] -ieq "start")  
        {  
            Write-Host `r`nIssuing start command to $app.Name...`r`n  
            $app.Start([Microsoft.BizTalk.ExplorerOM.ApplicationStartOption] "StartAll")  
            $Catalog.SaveChanges()  
        }  
  
        if ($args[0] -ieq "stop")  
        {  
            Write-Host `r`nIssuing stop command to $app.Name...`r`n  
            $app.Stop([Microsoft.BizTalk.ExplorerOM.ApplicationStopOption] "StopAll")  
            $Catalog.SaveChanges()  
        }  
  
    }  
}  
```  
  
 <span data-ttu-id="ed6b7-141">脚本中需要与 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 示例相同的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="ed6b7-141">The script expects the same command-line arguments as the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] sample.</span></span> <span data-ttu-id="ed6b7-142">下面是一个运行 Windows PowerShell 脚本以启动部署的 BizTalk 应用程序的示例：</span><span class="sxs-lookup"><span data-stu-id="ed6b7-142">Here is an example of running the Windows PowerShell script to start a deployed BizTalk application:</span></span>  
  
```  
PS C:\> .\ApplicationManager.ps1 start MyBizTalkApp  
  
Issuing start command to MyBizTalkApp ...  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed6b7-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed6b7-143">See Also</span></span>  
 [<span data-ttu-id="ed6b7-144">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="ed6b7-144">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)