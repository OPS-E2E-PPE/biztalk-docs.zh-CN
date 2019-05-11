---
title: CBR （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add16683-4090-4854-8d6e-923b58937e9d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b93831275f2ae12bdef54f9116a2242d9cc52d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357836"
---
# <a name="cbr-biztalk-server-sample"></a><span data-ttu-id="0c8c9-102">CBR （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="0c8c9-102">CBR (BizTalk Server Sample)</span></span>
<span data-ttu-id="0c8c9-103">CBR 示例演示如何使用**ExplorerOM**管理对象来添加和配置新发送端口的 BizTalk 消息基于内容的路由。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-103">The CBR sample demonstrates using the **ExplorerOM** administrative objects to add and configure new send ports for content-based routing of BizTalk messages.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0c8c9-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="0c8c9-104">Prerequisites</span></span>  

- <span data-ttu-id="0c8c9-105">此示例要求通过运行位于中的 setup.bat 来部署 CBRSample \<*示例路径*\>\Messaging\CBRSample 目录。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-105">This sample requires that the CBRSample be deployed by running setup.bat located in the \<*Samples Path*\>\Messaging\CBRSample directory.</span></span>  

- <span data-ttu-id="0c8c9-106">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="0c8c9-107">Windows PowerShell 脚本示例需要 Windows PowerShell 执行策略才能允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-107">The Windows PowerShell script example requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="0c8c9-108">有关详细信息，请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-108">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="0c8c9-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="0c8c9-109">What This Sample Does</span></span>  
 <span data-ttu-id="0c8c9-110">此示例演示如何使用中的管理对象**Microsoft.BizTalk.ExplorerOM**命名空间将两个新端口添加到 CBRApplication 示例。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-110">This sample demonstrates using the administrative objects in the **Microsoft.BizTalk.ExplorerOM** namespace to add two new ports to the CBRApplication sample.</span></span> <span data-ttu-id="0c8c9-111">这些新端口是 CBRApplication 的示例端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-111">These new ports are example ports for CBRApplication.</span></span> <span data-ttu-id="0c8c9-112">通过使用 HTTP 适配器，将消息路由到假设的 HTTP Web 服务地址配置的端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-112">The ports are configured to route messages to a hypothetical HTTP Web service address by using the HTTP adapter.</span></span> <span data-ttu-id="0c8c9-113">本示例演示如何使用 **ExplorerOM** 对象完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c8c9-113">The sample demonstrates the following operations using the **ExplorerOM** objects:</span></span>  

-   <span data-ttu-id="0c8c9-114">使用**AddNewSendPort**方法**应用程序**类添加名为 SendportUSOrders 到 CBRApplication 的新发送端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-114">Using the **AddNewSendPort** method of the **Application** class to add a new send port called SendportUSOrders to CBRApplication.</span></span> <span data-ttu-id="0c8c9-115">端口配置为使用 HTTP 适配器与假设的 Web 地址的传输。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-115">The port is configured to use the HTTP adapter for transport with a hypothetical Web address.</span></span>  

-   <span data-ttu-id="0c8c9-116">将筛选器添加到订阅美国的 CBRApplication 中的消息的 SendportUSOrders国家/地区代码值为 100。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-116">Adding a filter to SendportUSOrders that subscribes to messages in CBRApplication with the U.S. Country Code value of 100.</span></span>  

-   <span data-ttu-id="0c8c9-117">为 SendportUSOrders 的出站映射到添加 CBRApplication 映射，将基于美国的消息。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-117">Adding the CBRApplication map for transforming U.S.-based messages to the outbound maps for SendportUSOrders.</span></span>  

-   <span data-ttu-id="0c8c9-118">添加名为 SendportCANOrders CBRApplication，并将其配置为使用 HTTP 适配器与假设的 Web 地址的传输到新的发送端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-118">Adding a new send port called SendportCANOrders to CBRApplication and configuring it to use the HTTP adapter for transport with a hypothetical Web address.</span></span>  

-   <span data-ttu-id="0c8c9-119">将筛选器添加到订阅加拿大国家/地区代码值为 200 的 CBRApplication 中消息的 SendportCANOrders。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-119">Adding a filter to SendportCANOrders that subscribes to messages in CBRApplication with the Canada Country Code value of 200.</span></span>  

-   <span data-ttu-id="0c8c9-120">为 SendportCANOrders 的出站映射到添加 CBRApplication 映射，将基于加拿大的消息。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-120">Adding the CBRApplication map for transforming Canadian-based messages to the outbound maps for SendportCANOrders.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="0c8c9-121">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="0c8c9-121">Where To Find This Sample</span></span>  
 <span data-ttu-id="0c8c9-122">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="0c8c9-122">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="0c8c9-123">\<*Samples Path*\>\Admin\ExplorerOM\CBR</span><span class="sxs-lookup"><span data-stu-id="0c8c9-123">\<*Samples Path*\>\Admin\ExplorerOM\CBR</span></span>  

 <span data-ttu-id="0c8c9-124">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="0c8c9-124">The following table shows the files in this sample and describes their purpose.</span></span>  


|           <span data-ttu-id="0c8c9-125">文件</span><span class="sxs-lookup"><span data-stu-id="0c8c9-125">File(s)</span></span>            |                                                 <span data-ttu-id="0c8c9-126">Description</span><span class="sxs-lookup"><span data-stu-id="0c8c9-126">Description</span></span>                                                  |
|------------------------------|--------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="0c8c9-127">ContentBasedRouting.cs</span><span class="sxs-lookup"><span data-stu-id="0c8c9-127">ContentBasedRouting.cs</span></span>    | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] <span data-ttu-id="0c8c9-128">此示例中演示的操作的源文件。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-128">source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="0c8c9-129">CBR.sln, CBR.csproj, CBR.suo</span><span class="sxs-lookup"><span data-stu-id="0c8c9-129">CBR.sln, CBR.csproj, CBR.suo</span></span> |                                  <span data-ttu-id="0c8c9-130">示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-130">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="0c8c9-131">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="0c8c9-131">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="0c8c9-132">生成示例</span><span class="sxs-lookup"><span data-stu-id="0c8c9-132">To build this sample</span></span>  

1. <span data-ttu-id="0c8c9-133">请确保已完成生成、 部署和配置 CBRSample 的步骤。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-133">Make sure you have completed the steps for building, deploying, and configuring the CBRSample.</span></span> <span data-ttu-id="0c8c9-134">中提供了这些步骤[CBRSample （BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-134">Those steps are provided in [CBRSample (BizTalk Server Sample)](../core/cbrsample-biztalk-server-sample.md).</span></span>  

2. <span data-ttu-id="0c8c9-135">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 CBR.sln。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-135">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file CBR.sln.</span></span>  

3. <span data-ttu-id="0c8c9-136">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-136">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="0c8c9-137">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="0c8c9-137">To run this sample</span></span>  

1. <span data-ttu-id="0c8c9-138">打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台并导航至**CBRApplication**节点。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and navigate to the **CBRApplication** node.</span></span>  

2. <span data-ttu-id="0c8c9-139">展开**CBRApplication**节点，验证**发送端口**节点当前是否列出为 CBRUSSendPort 和 CBRCANSendPort 的只有两个端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-139">Expand the **CBRApplication** node to verify that the **Send Ports** node currently has only two ports listed as CBRUSSendPort and CBRCANSendPort.</span></span>  

3. <span data-ttu-id="0c8c9-140">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="0c8c9-140">Open a command window and navigate to the following folder:</span></span>  

    <span data-ttu-id="0c8c9-141">\<*Samples Path*\>\Admin\ExplorerOM\CBR\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="0c8c9-141">\<*Samples Path*\>\Admin\ExplorerOM\CBR\bin\Debug</span></span>  

4. <span data-ttu-id="0c8c9-142">运行文件 CBR.exe。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-142">Run the file CBR.exe.</span></span>  

5. <span data-ttu-id="0c8c9-143">按 F5 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来刷新视图下的**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-143">Press F5 in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to refresh the view under the **Send Ports** node.</span></span> <span data-ttu-id="0c8c9-144">现在应看到此示例添加到 CBRApplication 的两个新端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-144">You should now see the two new ports added to CBRApplication by this sample.</span></span> <span data-ttu-id="0c8c9-145">它们被名为 SendportUSOrders 和 SendportCANOrders。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-145">They are called SendportUSOrders and SendportCANOrders.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="0c8c9-146">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="0c8c9-146">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="0c8c9-147">以下 Windows PowerShell 脚本可用于演示 **ExplorerOM** 类的相同功能。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-147">The following Windows PowerShell script can be used to demonstrate the same features of the **ExplorerOM** classes.</span></span> <span data-ttu-id="0c8c9-148">但是，由于**外**方法**SendPort.OutboundTranforms**集合标记中的内部**ExplorerOM**它不能直接从调用的程序集Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-148">However, because the **Add** method for the **SendPort.OutboundTranforms** collection is marked Internal in the **ExplorerOM** assembly it cannot be called directly from Windows PowerShell.</span></span> <span data-ttu-id="0c8c9-149">此 Windows PowerShell 脚本演示如何使用 Windows PowerShell 中的 BizTalk WMI 提供程序将出站转换映射添加到新的端口。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-149">This Windows PowerShell script demonstrates using the BizTalk WMI Provider from Windows PowerShell to add the outbound transform map to the new port.</span></span>  

```  
Function WMI_AddOutboundTransformToPort($transform,$strPortName)  
{  
    Write-Host "WMI Processing Transform...`r`nPortName `:"$strPortName  
    Write-Host "Transform `:"$transform.AssemblyQualifiedName  

    $WMIsendport = get-wmiobject MSBTS_SendPort -filter "Name=`"$strPortName`"" -namespace root\microsoftbiztalkserver  
    $WMIsendport.OutboundTransforms = $transform.AssemblyQualifiedName  
    [Void] $WMIsendport.Put()  
    [Void] $WMIsendport.Start()  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

$CBRApp = $Catalog.Applications["CBRApplication"]  

if ($CBRApp -eq $null)  
{  
    Write-Host "`r`nFailed to find `"CBRApplication`" deployed on this BizTalk server."  
    Write-Host "You must deploy the SDK\Samples\Messaging\CBRSample in order to test this script.`r`n"  
}  
else  
{  
    #=== Register a trap handler for any exceptions ===#  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #===================================#  
    #=== Create the U.S. Orders Port ===#  
    #===================================#  

    $USPort = $CBRApp.AddNewSendPort($false,$false)  
    $USPort.Name = "SendportUSOrders"  
    $USPort.PrimaryTransport.TransportType = $Catalog.ProtocolTypes["HTTP"]  
    $USPort.PrimaryTransport.Address = "http://process_orders_US.asp"  
    $USPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== add the filter to subscribe to messages with U.S country code 100 ===#  

    $USPort.Filter = "<Filter><Group>" +  
                     "<Statement Property='BTS.ReceivePortName' Operator='0' Value='ReceivePortPO'/>" +   
                     "<Statement Property='CBRSample.CountryCode' Operator='0' Value='100'/>" +  
                     "</Group></Filter>"  

    Write-Host("`r`nAdding " + $UsPort.Name + " to catalog ...")  
    $Catalog.SaveChanges()  

    #=========================================================================================#  
    #=== SendPortTranformCollection::Add is marked internal in ExplorerOM for some reason. ===#  
    #=== Use WMI to set this as a workaround through PowerShell.                           ===#  
    #=========================================================================================#  

    WMI_AddOutboundTransformToPort $Catalog.Transforms["CBRSample.CBRInput2USMap"] $USport.Name  

    #=====================================#  
    #=== Create the Canada Orders Port ===#  
    #=====================================#  

    $CanadaPort = $CBRApp.AddNewSendPort($false,$false)  
    $CanadaPort.Name = "SendportCANOrders"  
    $CanadaPort.PrimaryTransport.TransportType = $Catalog.ProtocolTypes["HTTP"]  
    $CanadaPort.PrimaryTransport.Address = "http://process_orders_CAN.asp"  
    $CanadaPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== add the filter to subscribe to messages with U.S country code 100 ===#  

    $CanadaPort.Filter = "<Filter><Group>" +  
                     "<Statement Property='BTS.ReceivePortName' Operator='0' Value='ReceivePortPO'/>" +   
                     "<Statement Property='CBRSample.CountryCode' Operator='0' Value='200'/>" +  
                     "</Group></Filter>"  

    Write-Host("`r`nAdding " + $UsPort.Name + " to catalog ...")  
    $Catalog.SaveChanges()  

    #=========================================================================================#  
    #=== SendPortTranformCollection::Add is marked internal in ExplorerOM for some reason. ===#  
    #=== Use WMI to set this as a workaround through PowerShell.                           ===#  
    #=========================================================================================#  

    WMI_AddOutboundTransformToPort $Catalog.Transforms["CBRSample.CBRInput2CANMap"] $CanadaPort.Name  

    Write-Host  
}  
```  

 <span data-ttu-id="0c8c9-150">下面是运行 Windows PowerShell 脚本以创建两个新端口的示例输出。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-150">Here is an example output from running the Windows PowerShell script to create the two new ports.</span></span> <span data-ttu-id="0c8c9-151">此外可以在中验证新端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上文所述的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0c8c9-151">The new ports can also be verified in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console as mentioned above.</span></span>  

```  
PS C:\> .\CBR.ps1  

Adding SendportUSOrders to catalog ...  
WMI Processing Transform...  
PortName : SendportUSOrders  
Transform : CBRSample.CBRInput2USMap,CBRSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ba2e1651515c6db7  

Adding SendportUSOrders to catalog ...  
WMI Processing Transform...  
PortName : SendportCANOrders  
Transform : CBRSample.CBRInput2CANMap,CBRSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ba2e1651515c6db7  

```  

## <a name="see-also"></a><span data-ttu-id="0c8c9-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8c9-152">See Also</span></span>  
 <span data-ttu-id="0c8c9-153">[Admin-explorerom （BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="0c8c9-153">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="0c8c9-154">CBRSample（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="0c8c9-154">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)