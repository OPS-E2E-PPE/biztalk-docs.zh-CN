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
# <a name="cbr-biztalk-server-sample"></a>CBR （BizTalk Server 示例）
CBR 示例演示如何使用**ExplorerOM**管理对象来添加和配置新发送端口的 BizTalk 消息基于内容的路由。  

## <a name="prerequisites"></a>先决条件  

- 此示例要求通过运行位于中的 setup.bat 来部署 CBRSample \<*示例路径*\>\Messaging\CBRSample 目录。  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本示例需要 Windows PowerShell 执行策略才能允许脚本执行。 有关详细信息，请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用中的管理对象**Microsoft.BizTalk.ExplorerOM**命名空间将两个新端口添加到 CBRApplication 示例。 这些新端口是 CBRApplication 的示例端口。 通过使用 HTTP 适配器，将消息路由到假设的 HTTP Web 服务地址配置的端口。 本示例演示如何使用 **ExplorerOM** 对象完成以下操作：  

-   使用**AddNewSendPort**方法**应用程序**类添加名为 SendportUSOrders 到 CBRApplication 的新发送端口。 端口配置为使用 HTTP 适配器与假设的 Web 地址的传输。  

-   将筛选器添加到订阅美国的 CBRApplication 中的消息的 SendportUSOrders国家/地区代码值为 100。  

-   为 SendportUSOrders 的出站映射到添加 CBRApplication 映射，将基于美国的消息。  

-   添加名为 SendportCANOrders CBRApplication，并将其配置为使用 HTTP 适配器与假设的 Web 地址的传输到新的发送端口。  

-   将筛选器添加到订阅加拿大国家/地区代码值为 200 的 CBRApplication 中消息的 SendportCANOrders。  

-   为 SendportCANOrders 的出站映射到添加 CBRApplication 映射，将基于加拿大的消息。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 本示例位于以下 SDK 位置中：  

 \<*Samples Path*\>\Admin\ExplorerOM\CBR  

 下表显示了本示例中的文件及其用途说明：  


|           文件            |                                                 Description                                                  |
|------------------------------|--------------------------------------------------------------------------------------------------------------|
|    ContentBasedRouting.cs    | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 此示例中演示的操作的源文件。 |
| CBR.sln, CBR.csproj, CBR.suo |                                  示例的解决方案文件和项目文件。                                  |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  

#### <a name="to-build-this-sample"></a>生成示例  

1. 请确保已完成生成、 部署和配置 CBRSample 的步骤。 中提供了这些步骤[CBRSample （BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)。  

2. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 CBR.sln。  

3. 在“生成”  菜单上，单击“生成解决方案” 。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台并导航至**CBRApplication**节点。  

2. 展开**CBRApplication**节点，验证**发送端口**节点当前是否列出为 CBRUSSendPort 和 CBRCANSendPort 的只有两个端口。  

3. 打开命令窗口并导航到以下文件夹：  

    \<*Samples Path*\>\Admin\ExplorerOM\CBR\bin\Debug  

4. 运行文件 CBR.exe。  

5. 按 F5 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来刷新视图下的**发送端口**节点。 现在应看到此示例添加到 CBRApplication 的两个新端口。 它们被名为 SendportUSOrders 和 SendportCANOrders。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 脚本可用于演示 **ExplorerOM** 类的相同功能。 但是，由于**外**方法**SendPort.OutboundTranforms**集合标记中的内部**ExplorerOM**它不能直接从调用的程序集Windows PowerShell。 此 Windows PowerShell 脚本演示如何使用 Windows PowerShell 中的 BizTalk WMI 提供程序将出站转换映射添加到新的端口。  

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

 下面是运行 Windows PowerShell 脚本以创建两个新端口的示例输出。 此外可以在中验证新端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上文所述的管理控制台。  

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

## <a name="see-also"></a>请参阅  
 [Admin-explorerom （BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)   
 [CBRSample（BizTalk Server 示例）](../core/cbrsample-biztalk-server-sample.md)