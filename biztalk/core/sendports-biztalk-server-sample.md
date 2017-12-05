---
title: "发送端口 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b84f96a2-b749-4fe0-be15-e4dd13eff66f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd7c03e4cfa586a0dddd2579931bd5f30d293fa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="sendports-biztalk-server-sample"></a><span data-ttu-id="5e455-102">SendPorts（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="5e455-102">SendPorts (BizTalk Server Sample)</span></span>
<span data-ttu-id="5e455-103">发送端口示例演示如何枚举使用和管理发送端口**Microsoft.BizTalk.ExplorerOM**管理类。</span><span class="sxs-lookup"><span data-stu-id="5e455-103">The SendPorts sample demonstrates how to enumerate and manage send ports by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5e455-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="5e455-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="5e455-105">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="5e455-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="5e455-106">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="5e455-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="5e455-107">有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="5e455-107">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5e455-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="5e455-108">What This Sample Does</span></span>  
 <span data-ttu-id="5e455-109">此示例演示如何使用**BtsCatalogExplorer**和**发送端口**类从**Microsoft.BizTalk.ExplorerOM**命名空间以管理在发送端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="5e455-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPort** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send ports in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="5e455-110">本示例是使用 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 编写的。</span><span class="sxs-lookup"><span data-stu-id="5e455-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="5e455-111">本主题中还包含 Windows PowerShell 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="5e455-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="5e455-112">本示例将演示以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e455-112">The sample demonstrates the following operations:</span></span>  
  
1.  <span data-ttu-id="5e455-113">使用连接到 BizTalk 管理数据库**BtsCatalogExplorer**类。</span><span class="sxs-lookup"><span data-stu-id="5e455-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
2.  <span data-ttu-id="5e455-114">创建两个新的发送端口的命名 myStaticOnewaySendPort1 和 myDynamicTwowaySendPort1。</span><span class="sxs-lookup"><span data-stu-id="5e455-114">Creating two new send ports named myStaticOnewaySendPort1 and myDynamicTwowaySendPort1.</span></span> <span data-ttu-id="5e455-115">myStaticOnewaySendPort1，正如其名，是静态单向发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-115">myStaticOnewaySendPort1, as its name implies, is a static one-way send port.</span></span>  <span data-ttu-id="5e455-116">它创建了示例目标 URL http://sample1 与使用 HTTP 传输。</span><span class="sxs-lookup"><span data-stu-id="5e455-116">It is created to use the HTTP transport with an example destination URL http://sample1.</span></span> <span data-ttu-id="5e455-117">myDynamicTwowaySendPort1 创建为动态双向发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-117">myDynamicTwowaySendPort1 is created as a dynamic two-way send port.</span></span>  
  
3.  <span data-ttu-id="5e455-118">枚举 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-118">Enumerating send ports in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="5e455-119">此示例枚举应包括两个新发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-119">This example enumeration should include the two new send ports.</span></span>  
  
4.  <span data-ttu-id="5e455-120">删除这两个新发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-120">Deleting the two new send ports.</span></span>  
  
5.  <span data-ttu-id="5e455-121">配置新发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-121">Configuring the new send ports.</span></span> <span data-ttu-id="5e455-122">此示例演示的配置应用于名为 myStaticOnewaySendPort1 的示例发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e455-122">The configurations demonstrated by the sample are applied to the example send port named myStaticOnewaySendPort1.</span></span> <span data-ttu-id="5e455-123">此示例应用的配置包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="5e455-123">The configurations applied by the sample include the following:</span></span>  
  
    -   <span data-ttu-id="5e455-124">启用**端口处理前的请求消息**用于跟踪消息正文的选项。</span><span class="sxs-lookup"><span data-stu-id="5e455-124">Enabling the **Request message before port processing** option for tracking message bodies.</span></span>  
  
    -   <span data-ttu-id="5e455-125">启用**端口处理后的请求消息**用于跟踪消息正文的选项。</span><span class="sxs-lookup"><span data-stu-id="5e455-125">Enabling the **Request message after port processing** option for tracking message bodies.</span></span>  
  
    -   <span data-ttu-id="5e455-126">指定发送端口用于传出消息的加密证书。</span><span class="sxs-lookup"><span data-stu-id="5e455-126">Specifying an encryption certificate for the send port to use on outgoing messages.</span></span>  
  
    -   <span data-ttu-id="5e455-127">针对一组消息指定用于登记的筛选器。</span><span class="sxs-lookup"><span data-stu-id="5e455-127">Specifying a filter for enlistment against a set of messages.</span></span>  
  
    -   <span data-ttu-id="5e455-128">添加映射以转换消息。</span><span class="sxs-lookup"><span data-stu-id="5e455-128">Adding a map to transform the messages.</span></span>  
  
6.  <span data-ttu-id="5e455-129">更改两个新发送端口上的发送端口状态。</span><span class="sxs-lookup"><span data-stu-id="5e455-129">Changing send port status on the two new send ports.</span></span>  <span data-ttu-id="5e455-130">执行本示例将对 myStaticOnewaySendPort1 进行以下状态更改：</span><span class="sxs-lookup"><span data-stu-id="5e455-130">The execution of the sample will make the following status changes on the myStaticOnewaySendPort1:</span></span>  
  
    -   <span data-ttu-id="5e455-131">将状态更改为已启动。</span><span class="sxs-lookup"><span data-stu-id="5e455-131">Change the status to started.</span></span>  
  
    -   <span data-ttu-id="5e455-132">将状态更改为已停止。</span><span class="sxs-lookup"><span data-stu-id="5e455-132">Change the status to stopped.</span></span>  
  
    -   <span data-ttu-id="5e455-133">将状态更改为已绑定。</span><span class="sxs-lookup"><span data-stu-id="5e455-133">Change the status to bound.</span></span> <span data-ttu-id="5e455-134">绑定状态与注销状态相同。</span><span class="sxs-lookup"><span data-stu-id="5e455-134">The bound status is the same as unenlisted.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5e455-135">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="5e455-135">Where To Find This Sample</span></span>  
 <span data-ttu-id="5e455-136">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="5e455-136">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="5e455-137">\<*示例路径*\>\Admin\ExplorerOM\SendPorts</span><span class="sxs-lookup"><span data-stu-id="5e455-137">\<*Samples Path*\>\Admin\ExplorerOM\SendPorts</span></span>  
  
 <span data-ttu-id="5e455-138">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="5e455-138">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5e455-139">文件</span><span class="sxs-lookup"><span data-stu-id="5e455-139">File(s)</span></span>|<span data-ttu-id="5e455-140">Description</span><span class="sxs-lookup"><span data-stu-id="5e455-140">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e455-141">SendPorts.cs</span><span class="sxs-lookup"><span data-stu-id="5e455-141">SendPorts.cs</span></span>|<span data-ttu-id="5e455-142">本示例中演示的操作所需的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。</span><span class="sxs-lookup"><span data-stu-id="5e455-142">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="5e455-143">SendPorts.sln、SendPorts.csproj、SendPorts.suo</span><span class="sxs-lookup"><span data-stu-id="5e455-143">SendPorts.sln, SendPorts.csproj, SendPorts.suo</span></span>|<span data-ttu-id="5e455-144">示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="5e455-144">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="5e455-145">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="5e455-145">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="5e455-146">生成示例</span><span class="sxs-lookup"><span data-stu-id="5e455-146">To build this sample</span></span>  
  
1.  <span data-ttu-id="5e455-147">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 SendPorts.sln。</span><span class="sxs-lookup"><span data-stu-id="5e455-147">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPorts.sln.</span></span>  
  
2.  <span data-ttu-id="5e455-148">在主菜单中，单击**生成**，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="5e455-148">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="5e455-149">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="5e455-149">To run this sample</span></span>  
  
1.  <span data-ttu-id="5e455-150">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="5e455-150">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="5e455-151">\<*示例路径*\>\Admin\ExplorerOM\SendPorts\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="5e455-151">\<*Samples Path*\>\Admin\ExplorerOM\SendPorts\bin\Debug</span></span>  
  
2.  <span data-ttu-id="5e455-152">运行文件 SendPorts.exe。</span><span class="sxs-lookup"><span data-stu-id="5e455-152">Run the file SendPorts.exe.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="5e455-153">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="5e455-153">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="5e455-154">以下 Windows PowerShell 脚本片段可以用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="5e455-154">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
Function CreateSendPorts($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  
  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  
  
    #=== create a new static one-way send port using HTTP transport ===#  
  
    $myStaticOnewaySendPort = $Catalog.AddNewSendPort($false,$false)  
    $myStaticOnewaySendPort.Name = "myStaticOnewaySendPort1"  
    $myStaticOnewaySendPort.PrimaryTransport.TransportType = $catalog.ProtocolTypes["HTTP"]  
    $myStaticOnewaySendPort.PrimaryTransport.Address = "http://sample1"  
    $myStaticOnewaySendPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  
  
    #=== create a new dynamic two-way send port ===#  
  
    $myDynamicTwowaySendPort = $catalog.AddNewSendPort($true,$true)  
    $myDynamicTwowaySendPort.Name = "myDynamicTwowaySendPort1";  
    $myDynamicTwowaySendPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"];  
    $myDynamicTwowaySendPort.ReceivePipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLReceive"];  
  
    #=== Persist new ports to BizTalk configuration database ===#  
  
    Write-Host Adding $myStaticOnewaySendPort.Name...  
    Write-Host Adding $myDynamicTwowaySendPort.Name...  
    $catalog.SaveChanges();  
    Write-Host "`r`nCreateSendPorts() completed."  
}  
  
Function DeleteSendPorts($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  
  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  
  
    #=== Delete this sample's new send ports by name ===#  
  
    $Catalog.RemoveSendPort($Catalog.SendPorts["myStaticOnewaySendPort1"])  
    $Catalog.RemoveSendPort($Catalog.SendPorts["myDynamicTwowaySendPort1"])  
  
    #=== Persist changes to BizTalk configuration database ===#  
  
    $catalog.SaveChanges();  
    Write-Host "DeleteSendPorts() completed."  
}  
  
Function EnumerateSendPorts($Catalog)  
{  
    #=== Display all send ports and their status info ===#  
  
    $catalog.SendPorts | format-table -Property Name, Status -autosize  
  
    Write-Host "EnumerateSendPorts`(`) completed."  
}  
  
Function ConfigureSendPort($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  
  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  
  
    $sendport = $catalog.SendPorts["myStaticOnewaySendPort1"];  
  
    #=== specify tracking settings for tracking ===#  
  
    Write-Host $sendport.Name: Enabling BeforeSendPipeline and AfterSendPipeline message body tracking.  
    $sendport.Tracking = ([Microsoft.BizTalk.ExplorerOM.TrackingTypes] "BeforeSendPipeline" -bor   
                         [Microsoft.BizTalk.ExplorerOM.TrackingTypes] "AfterSendPipeline")  
  
    #=== specify an encryption certificate for outgoing messages ===#  
  
    Write-Host $sendport.Name: Adding a encryption certificate  
    foreach ($certificate in $catalog.Certificates)  
    {  
        if ($certificate.UsageType -eq [Microsoft.BizTalk.ExplorerOM.CertUsageType] "Encryption")  
        {  
            $sendport.EncryptionCert = $certificate  
        }  
    }  
  
    #=== specify filters for content-based routing ===#  
    Write-Host $sendport.Name: Adding a filter  
    $sendport.Filter = "<Filter><Group>" +  
                       "<Statement Property='SMTP.Subject' Operator='0' Value='Purchase Order'/>" +  
                       "<Statement Property='SMTP.From' Operator='0' Value='Customer'/>" +  
                       "</Group></Filter>"  
  
    #=== specify transform maps for document normalization ===#  
  
    foreach ($transform in $catalog.Transforms)  
    {  
        if (($transform.SourceSchema.FullName -ieq "myPO") -and (transform.TargetSchema.FullName -ieq "partnerPO"))  
        {  
            Write-Host $sendport.Name: Adding a transform  
            $sendport.OutboundTransforms.Add($transform)  
        }  
    }  
  
    #=== Persist all changes to BizTalk configuration database ===#  
  
    Write-Host $sendport.Name: Saving changes  
    $catalog.SaveChanges();  
    Write-Host "`r`nConfigureSendPort() completed."  
}  
  
Function ChangeSendPortStatus($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  
  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  
  
    $sendport = $catalog.SendPorts["myStaticOnewaySendPort1"];  
  
    #=== start the send port to begin processing messages ===#  
  
    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Started"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  
  
    #=== stop the send port to stop processing and suspend messages ===#  
  
    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Stopped"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  
  
    #=== unenlist the send port to stop processing and discard messages ===#  
  
    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Bound"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)`(Unenlisted`)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  
}  
  
#=== Main Script Body ===#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== Exercise the CreateSendPorts function to create the two new ports ===#  
  
Write-Host "`r`n========================="  
Write-Host "=== CreateSendPorts`(`) ==="  
Write-Host "=========================`r`n"  
CreateSendPorts $Catalog  
  
#=== Enumerate all send ports to view the two new ports ===#  
  
Write-Host "`r`n============================"  
Write-Host "=== EnumerateSendPorts`(`) ==="  
Write-Host "============================`r`n"  
EnumerateSendPorts $Catalog  
  
#=== Add some configuration to the static send port ===#  
  
Write-Host "`r`n==========================="  
Write-Host "=== ConfigureSendPort`(`) ==="  
Write-Host "===========================`r`n"  
ConfigureSendPort $Catalog  
  
#=== Cycle through some status changes on the static send port ===#  
  
Write-Host "`r`n=============================="  
Write-Host "=== ChangeSendPortStatus`(`) ==="  
Write-Host "==============================`r`n"  
ChangeSendPortStatus $Catalog  
  
#=== Delete the two new ports ===#  
  
Write-Host "`r`n========================="  
Write-Host "=== DeleteSendPorts`(`) ==="  
Write-Host "=========================`r`n"  
DeleteSendPorts $Catalog  
  
Write-Host  
```  
  
 <span data-ttu-id="5e455-155">下面是预期的示例从运行 Windows PowerShell 脚本示例的输出。</span><span class="sxs-lookup"><span data-stu-id="5e455-155">Here is example expected output from running the Windows PowerShell script sample.</span></span>  
  
```  
PS C:\> & 'C:\SendPorts.ps1'  
  
=========================  
=== CreateSendPorts() ===  
=========================  
  
Adding myStaticOnewaySendPort1 ...  
Adding myDynamicTwowaySendPort1 ...  
  
CreateSendPorts() completed.  
  
============================  
=== EnumerateSendPorts() ===  
============================  
  
Name                      Status  
----                      ------  
ResendPort               Started  
HelloWorldSendPort       Started  
ToCustomerSendPort       Started  
CBRUSSendPort            Started  
CBRCANSendPort           Started  
SendportCANOrders          Bound  
myStaticOnewaySendPort1    Bound  
myDynamicTwowaySendPort1   Bound  
  
EnumerateSendPorts() completed.  
  
===========================  
=== ConfigureSendPort() ===  
===========================  
  
myStaticOnewaySendPort1 : Enabling BeforeSendPipeline and AfterSendPipeline message body tracking.  
myStaticOnewaySendPort1 : Adding a encryption certificate  
myStaticOnewaySendPort1 : Adding a filter  
myStaticOnewaySendPort1 : Saving changes  
  
ConfigureSendPort() completed.  
  
==============================  
=== ChangeSendPortStatus() ===  
==============================  
  
Changing myStaticOnewaySendPort1 status to Started ...  
Complete.  
Changing myStaticOnewaySendPort1 status to Stopped ...  
Complete.  
Changing myStaticOnewaySendPort1 status to Bound (Unenlisted)...  
Complete.  
  
=========================  
=== DeleteSendPorts() ===  
=========================  
  
DeleteSendPorts() completed.  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e455-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e455-156">See Also</span></span>  
 [<span data-ttu-id="5e455-157">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="5e455-157">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)