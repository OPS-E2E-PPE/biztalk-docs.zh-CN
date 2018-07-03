---
title: SendPorts （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b84f96a2-b749-4fe0-be15-e4dd13eff66f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6ef809104e1ce11385cb88d94547d0de496af1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009902"
---
# <a name="sendports-biztalk-server-sample"></a>SendPorts（BizTalk Server 示例）
SendPorts 示例演示如何枚举和管理通过使用发送端口**Microsoft.BizTalk.ExplorerOM**管理类。  

## <a name="prerequisites"></a>必要條件  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。 有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用**BtsCatalogExplorer**并**发送端口**类**Microsoft.BizTalk.ExplorerOM**命名空间以管理中的发送端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 本示例是使用 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 编写的。 本主题中还包含 Windows PowerShell 示例脚本。 本示例将演示以下操作：  

1. 通过使用连接到 BizTalk 管理数据库**BtsCatalogExplorer**类。  

2. 创建两个新发送端口命名为 myStaticOnewaySendPort1 和 myDynamicTwowaySendPort1。 myStaticOnewaySendPort1，正如其名，是一个静态单向发送端口。  创建与示例目标 URL 使用 HTTP 传输http://sample1。 myDynamicTwowaySendPort1 创建为动态双向发送端口。  

3. 枚举 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中的发送端口。 此示例枚举应包括两个新发送端口。  

4. 删除这两个新发送端口。  

5. 配置新发送端口。 此示例演示的配置应用于名为 myStaticOnewaySendPort1 的示例发送端口。 此示例应用的配置包括以下内容：  

   -   启用**端口处理前的请求消息**跟踪消息正文的选项。  

   -   启用**端口处理后的请求消息**跟踪消息正文的选项。  

   -   指定发送端口用于传出消息的加密证书。  

   -   针对一组消息指定用于登记的筛选器。  

   -   添加映射以转换消息。  

6. 更改两个新发送端口上的发送端口状态。  执行本示例将对 myStaticOnewaySendPort1 进行以下状态更改：  

   -   将状态更改为已启动。  

   -   将状态更改为已停止。  

   -   将状态更改为已绑定。 绑定状态与注销状态相同。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 本示例位于以下 SDK 位置中：  

 \<*示例路径*\>\Admin\ExplorerOM\SendPorts  

 下表显示了本示例中的文件及其用途说明：  


|                    文件                     |                                                 Description                                                  |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                  SendPorts.cs                  | 本示例中演示的操作所需的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。 |
| SendPorts.sln、SendPorts.csproj、SendPorts.suo |                                  示例的解决方案文件和项目文件。                                  |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  

#### <a name="to-build-this-sample"></a>生成示例  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 SendPorts.sln。  

2. 在主菜单上，单击**构建**，然后单击**生成解决方案**。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  打开命令窗口并导航到以下文件夹：  

     \<*示例路径*\>\Admin\ExplorerOM\SendPorts\bin\Debug  

2.  运行文件 SendPorts.exe。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 脚本片段可用于演示的相同功能**ExplorerOM**类：  

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

 下面是从运行 Windows PowerShell 脚本示例的预期的示例输出。  

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

## <a name="see-also"></a>请参阅  
 [Admin-ExplorerOM（BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)