---
title: BrowsingArtifacts （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b63c0833-3445-4361-a8eb-63837017edf8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce76916af78a0bf7918f7e081752811d05758935
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997206"
---
# <a name="browsingartifacts-biztalk-server-sample"></a>BrowsingArtifacts（BizTalk Server 示例）
BrowsingArtifacts 示例演示如何枚举 BizTalk 项目和属性。  

## <a name="prerequisites"></a>必要條件  

- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  

- Windows PowerShell 脚本示例需要 Windows PowerShell 执行策略才能允许脚本执行。 有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何使用**BtsCatalogExplorer**类派生**Microsoft.BizTalk.ExplorerOM**命名空间来枚举项目并报告其属性。 在此示例生成报告中包含以下项目： 业务流程、 端口、 程序集、 参与方和转换。 该示例是使用 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 编写的。 本主题中还包含一个 Windows PowerShell 示例脚本。  

## <a name="where-to-find-this-sample"></a>本示例的所在位置  
 本示例位于以下 SDK 位置中：  

 \<*示例路径*\>\Admin\ExplorerOM\BrowsingArtifacts  

 下表显示了本示例中的文件及其用途说明：  


|                                文件                                 |                                                 Description                                                  |
|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                          BrowsingArtifacts.cs                          | 本示例中演示的操作所需的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。 |
| BrowsingArtifacts.sln、BrowsingArtifacts.csproj、BrowsingArtifacts.suo |                                  示例的解决方案文件和项目文件。                                  |

## <a name="building-and-running-this-sample"></a>生成并运行本示例  

#### <a name="to-build-this-sample"></a>生成示例  

1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案文件 BrowsingArtifacts.sln。  

2. 在“生成”  菜单上，单击“生成解决方案” 。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  打开命令窗口并导航到以下文件夹：  

     \<*示例路径*\>\Admin\ExplorerOM\BrowsingArtifacts\bin\Debug  

2.  运行文件 BrowsingArtifacts.exe。  

## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 脚本可用于演示的相同功能**ExplorerOM**类：  

```  
Function EnumOrchestrations($catalog)  
{  
    Write-Host `r`n======================  
    Write-Host ===  ORCHESTRATIONS  ===  
    Write-Host ======================`r`n   

    #=== Enumerating the assemblies and pulling orchestration information ===#  

    foreach($assembly in $catalog.Assemblies)  
    {  
        foreach($orch in $assembly.Orchestrations)  
        {  
            #=== We can’t report the host if it is not hosted or enlisted ===#  
            if ($orch.Status -ieq "Unenlisted")  
            {  
                Write-Host Name : $orch.Fullname`r`nHost : N/A`r`nStatus : $orch.Status  
            }  
            else  
            {  
                Write-Host Name : $orch.Fullname`r`nHost : $orch.Host.Name`r`nStatus : $orch.Status  
            }  

            #=== Reporting port types and operations ===#  
            foreach($port in $orch.Ports)  
            {  
                Write-Host "`tPort:"$port.PortType.FullName  

                foreach($portop in $port.PortType.Operations)  
                {  
                    Write-Host "`t`tOperation:"$portop.Name  
                }  
            }  

            #=== Reporting Used roles ===#  
            foreach($role in $orch.UsedRoles)  
            {  
                Write-Host "`tRole:"$role.Name"`("$role.ServiceLinkType"`)"  

                foreach($EnlistedParty in $role.EnlistedParties)  
                {  
                    Write-Host "`t`tParty:"$Enlistedparty.Party.Name  
                }  
            }  

            #=== Reporting implemented roles ===#  
            foreach($role in $orch.ImplementedRoles)  
            {  
                Write-Host "`tRole:"$role.Name"`("$role.ServiceLinkType"`)"  
            }  

            Write-Host  
        }  
    }  
}  

Function EnumOtherArtifacts($catalog)  
{  
    Write-Host `r`n======================  
    Write-Host "===   ASSEMBLIES   ==="  
    Write-Host ======================`r`n   

    foreach($assembly in $catalog.Assemblies)  
    {  
        Write-Host $assembly.Name  
    }  

    Write-Host `r`n======================  
    Write-Host "===     HOSTS      ==="  
    Write-Host ======================`r`n   

    foreach($btshost in $catalog.Hosts)  
    {  
        Write-Host $btshost.Name"`($($btshost.Type)`)"  
    }  

    Write-Host `r`n======================  
    Write-Host "===    PARTIES     ==="  
    Write-Host ======================`r`n   

    foreach($party in $catalog.Parties)  
    {  
        Write-Host $party.Name  

        foreach($sendport in $party.SendPorts)  
        {  
            Write-Host "`tSendPort:"$sendport.Name  
        }  

        foreach($alias in $party.Aliases)  
        {  
            Write-Host "`tAlias:"$alias.Name":"$alias.Qualifier"="$alias.Value  
        }  
    }  

    Write-Host `r`n======================  
    Write-Host "===   TRANSFORMS   ==="  
    Write-Host ======================`r`n   

    foreach($transform in $catalog.Transforms)  
    {  
        Write-Host $transform.FullName":`r`n`t"$transform.SourceSchema.Fullname"==>"$transform.TargetSchema.Fullname`r`n  
    }  
}  

#=== Main Script Body ===#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== All reporting is performed in the following two functions ===#  

EnumOrchestrations $Catalog  
EnumOtherArtifacts $Catalog  
```  

 以下是运行 Windows PowerShell 脚本的示例以及示例输出：  

```  
PS C:\> .\BrowsingArtifacts.ps1  

======================  
=== ORCHESTRATIONS ===  
======================  

Name : Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService  
Host : BizTalkServerApplication  
Status : Enlisted  

Name : Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService  
Host : BizTalkServerApplication  
Status : Enlisted  

Name : Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService  
Host : BizTalkServerApplication  
Status : Enlisted  

Name : EAIOrchestrations.EAIProcess  
Host : N/A  
Status : Unenlisted  
        Port: EAIOrchestrations.ReceiveReqType  
                Operation: Operation_1  
        Port: EAIOrchestrations.SendDeclineType  
                Operation: Operation_1  
        Port: EAIOrchestrations.SendToERPType  
                Operation: Operation_1  

Name : B2BOrchestrations.B2BProcess  
Host : BizTalkServerApplication  
Status : Started  
        Port: B2BOrchestrations.ReceivePO_Type  
                Operation: Operation_1  
        Port: B2BOrchestrations.SendPOConfirmed_Type  
                Operation: Operation_1  
        Port: B2BSchemas.localhost.Process_.Process  
                Operation: ReceivePO  
        Port: B2BOrchestrations.ReceiveASN_Type  
                Operation: Operation_1  
        Port: B2BOrchestrations.ReceiveInvoice_Type  
                Operation: Operation_1  
        Port: B2BOrchestrations.PortType_PaymentVoucherArchive  
                Operation: Operation_1  
        Port: B2BSchemas.localhost1.Payment_Service_.Payment_Service  
                Operation: ProcessPayment  
        Port: B2BOrchestrations.SendPaymentAck_Type  
                Operation: Operation_1  

======================  
===   ASSEMBLIES   ===  
======================  

Microsoft.BizTalk.GlobalPropertySchemas  
Microsoft.BizTalk.DefaultPipelines  
Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties  
MQSeries  
Microsoft.BizTalk.Hws.HwsPromotedProperties  
Microsoft.BizTalk.Hws.HwsSchemas  
Microsoft.BizTalk.KwTpm.StsDefaultPipelines  
Microsoft.BizTalk.KwTpm.RoleLinkTypes  
mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
Microsoft.BizTalk.Edi.BaseArtifacts  
Microsoft.BizTalk.Edi.EdiPipelines  
Microsoft.BizTalk.Edi.BatchingOrchestration  
Microsoft.BizTalk.Edi.RoutingOrchestration  
Microsoft.BizTalk.Edi.EdiIntPipelines  
EAISchemas  
EAIOrchestrations  
B2BSchemas  
B2BOrchestrations  
WCFArtifacts  
FFDisassemblerWalkthrough  
BTSWhitespaceTest  

======================  
===     HOSTS      ===  
======================  

BizTalkServerApplication (InProcess)  
BizTalkServerIsolatedHost (Isolated)  

======================  
===    PARTIES     ===  
======================  

PartyB  
        Alias: Organization : OrganizationName = PartyB  

======================  
===   TRANSFORMS   ===  
======================  

EAISchemas.FFRequestDeniedMap :  
         EAISchemas.FlatFileSchema1 ==> EAISchemas.RequestDenied  

EAISchemas.RequestDeniedMap :  
         EAISchemas.Request ==> EAISchemas.RequestDenied  

B2BSchemas.InvoiceToPayment :  
         B2BSchemas.CommonInvoice ==> B2BSchemas.localhost1.Reference  

B2BSchemas.MapToCommonPO :  
         B2BSchemas.PO ==> B2BSchemas.localhost.Reference  

BizTalkArtifacts.ConcatMap :  
         BizTalkArtifacts.InputSchema ==> BizTalkArtifacts.OutputSchema  

FFDisassemblerWalkthrough.Map1 :  
         FFDisassemblerWalkthrough.Body ==> FFDisassemblerWalkthrough.Body  

BTSWhitespaceTest.Map1 :  
         FFDisassemblerWalkthrough.Body ==> BTSWhitespaceTest.Schema1  
```  

## <a name="see-also"></a>请参阅  
 [Admin-ExplorerOM（BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)