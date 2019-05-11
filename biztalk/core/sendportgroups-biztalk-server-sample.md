---
title: SendPortGroups （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4510aa31-16c3-475a-98aa-b590e13ae189
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca073cdbe6bc7a32ce0168db227d2121980c92ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254428"
---
# <a name="sendportgroups-biztalk-server-sample"></a><span data-ttu-id="caa6a-102">SendPortGroups （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="caa6a-102">SendPortGroups (BizTalk Server Sample)</span></span>
<span data-ttu-id="caa6a-103">SendPortGroups 示例演示了如何枚举和管理通过使用发送端口组**Microsoft.BizTalk.ExplorerOM**管理类。</span><span class="sxs-lookup"><span data-stu-id="caa6a-103">The SendPortGroups sample demonstrates how to enumerate and manage send port groups by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="caa6a-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="caa6a-104">Prerequisites</span></span>  

- <span data-ttu-id="caa6a-105">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="caa6a-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="caa6a-106">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="caa6a-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="caa6a-107">有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="caa6a-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="caa6a-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="caa6a-108">What This Sample Does</span></span>  
 <span data-ttu-id="caa6a-109">此示例演示如何使用**BtsCatalogExplorer**并**发送端口组**类**Microsoft.BizTalk.ExplorerOM**命名空间以管理发送端口组在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="caa6a-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPortGroup** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send port groups in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="caa6a-110">在 Microsoft 中编写示例[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="caa6a-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="caa6a-111">本主题中还包含 Windows PowerShell 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="caa6a-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="caa6a-112">此示例演示了以下操作：</span><span class="sxs-lookup"><span data-stu-id="caa6a-112">The sample demonstrates the following operations:</span></span>  

- <span data-ttu-id="caa6a-113">通过使用连接到 BizTalk 管理数据库**BtsCatalogExplorer**类。</span><span class="sxs-lookup"><span data-stu-id="caa6a-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  

- <span data-ttu-id="caa6a-114">创建名为"My Send Port Group"的新发送端口组。</span><span class="sxs-lookup"><span data-stu-id="caa6a-114">Creating a new send port group named “My Send Port Group”.</span></span>  

- <span data-ttu-id="caa6a-115">枚举可显示新创建的发送端口组发送端口组。</span><span class="sxs-lookup"><span data-stu-id="caa6a-115">Enumerating send port groups to display the newly created send port group.</span></span>  

- <span data-ttu-id="caa6a-116">正在删除新发送端口组。</span><span class="sxs-lookup"><span data-stu-id="caa6a-116">Deleting the new send port group.</span></span>  

  <span data-ttu-id="caa6a-117">其他函数都位于该示例，但不是在中执行[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]版本。</span><span class="sxs-lookup"><span data-stu-id="caa6a-117">Additional functions are present in the sample but are not executed in the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span>  <span data-ttu-id="caa6a-118">中的 PowerShell 示例脚本演示了一些其他函数。</span><span class="sxs-lookup"><span data-stu-id="caa6a-118">Some of the additional functions are demonstrated in the PowerShell example script.</span></span> <span data-ttu-id="caa6a-119">其他函数演示以下功能：</span><span class="sxs-lookup"><span data-stu-id="caa6a-119">The additional functions demonstrate the following functionality:</span></span>  

- <span data-ttu-id="caa6a-120">将发送端口添加到新创建的发送端口组 （PowerShell 示例中介绍）。</span><span class="sxs-lookup"><span data-stu-id="caa6a-120">Adding a send port to the newly created send port group (covered in the PowerShell example).</span></span>  

- <span data-ttu-id="caa6a-121">从发送端口组 （PowerShell 示例中介绍） 中删除发送端口。</span><span class="sxs-lookup"><span data-stu-id="caa6a-121">Deleting a send port from the send port group (covered in the PowerShell example).</span></span>  

- <span data-ttu-id="caa6a-122">正在启动发送端口组。</span><span class="sxs-lookup"><span data-stu-id="caa6a-122">Starting the send port group.</span></span>  

- <span data-ttu-id="caa6a-123">正在停止发送端口组。</span><span class="sxs-lookup"><span data-stu-id="caa6a-123">Stopping the send port group.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="caa6a-124">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="caa6a-124">Where To Find This Sample</span></span>  
 <span data-ttu-id="caa6a-125">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="caa6a-125">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="caa6a-126">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups</span><span class="sxs-lookup"><span data-stu-id="caa6a-126">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups</span></span>  

 <span data-ttu-id="caa6a-127">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="caa6a-127">The following table shows the files in this sample and describes their purpose.</span></span>  


|                            <span data-ttu-id="caa6a-128">文件</span><span class="sxs-lookup"><span data-stu-id="caa6a-128">File(s)</span></span>                            |                                                 <span data-ttu-id="caa6a-129">Description</span><span class="sxs-lookup"><span data-stu-id="caa6a-129">Description</span></span>                                                  |
|---------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="caa6a-130">SendPortGroups.cs</span><span class="sxs-lookup"><span data-stu-id="caa6a-130">SendPortGroups.cs</span></span>                       | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] <span data-ttu-id="caa6a-131">此示例中演示的操作的源文件。</span><span class="sxs-lookup"><span data-stu-id="caa6a-131">source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="caa6a-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span><span class="sxs-lookup"><span data-stu-id="caa6a-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span></span> |                                  <span data-ttu-id="caa6a-133">示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="caa6a-133">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="caa6a-134">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="caa6a-134">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="caa6a-135">生成示例</span><span class="sxs-lookup"><span data-stu-id="caa6a-135">To build this sample</span></span>  

1. <span data-ttu-id="caa6a-136">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 SendPortGroups.sln。</span><span class="sxs-lookup"><span data-stu-id="caa6a-136">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPortGroups.sln.</span></span>  

2. <span data-ttu-id="caa6a-137">在解决方案资源管理器，双击**SendPortGroups.cs**打开示例代码。</span><span class="sxs-lookup"><span data-stu-id="caa6a-137">In Solution Explorer, double click **SendPortGroups.cs** to open the sample code.</span></span>  

3. <span data-ttu-id="caa6a-138">查找`root.ConnectionString`在`CreateSendPortGroup`函数。</span><span class="sxs-lookup"><span data-stu-id="caa6a-138">Find the `root.ConnectionString` in the `CreateSendPortGroup` function.</span></span>  <span data-ttu-id="caa6a-139">必须更改服务器规范以正确地指向托管 BizTalk 管理数据库的 SQL server。</span><span class="sxs-lookup"><span data-stu-id="caa6a-139">You must change the server specification to correctly point to the SQL server hosting your BizTalk Management database.</span></span>  <span data-ttu-id="caa6a-140">此外可以使用句点 （.） 来连接到本地 SQL server。</span><span class="sxs-lookup"><span data-stu-id="caa6a-140">You can also use a period (.) to connect to the local SQL server.</span></span>  <span data-ttu-id="caa6a-141">例如：</span><span class="sxs-lookup"><span data-stu-id="caa6a-141">For example:</span></span>  

   ```  
   root.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=.";  
   ```  

4. <span data-ttu-id="caa6a-142">重复步骤 3 的以下函数：</span><span class="sxs-lookup"><span data-stu-id="caa6a-142">Repeat step 3 for the following functions:</span></span>  

   -   <span data-ttu-id="caa6a-143">**EnumerateSendPortGroups**</span><span class="sxs-lookup"><span data-stu-id="caa6a-143">**EnumerateSendPortGroups**</span></span>  

   -   <span data-ttu-id="caa6a-144">**DeleteSendPortGroup**</span><span class="sxs-lookup"><span data-stu-id="caa6a-144">**DeleteSendPortGroup**</span></span>  

5. <span data-ttu-id="caa6a-145">保存**SendPortGroups.cs**。</span><span class="sxs-lookup"><span data-stu-id="caa6a-145">Save **SendPortGroups.cs**.</span></span>  

6. <span data-ttu-id="caa6a-146">在主菜单上，单击**构建**，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="caa6a-146">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="caa6a-147">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="caa6a-147">To run this sample</span></span>  

1.  <span data-ttu-id="caa6a-148">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="caa6a-148">Open a command window and navigate to the following folder:</span></span>  

     <span data-ttu-id="caa6a-149">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="caa6a-149">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span></span>  

2.  <span data-ttu-id="caa6a-150">运行文件 SendPortGroups.exe。</span><span class="sxs-lookup"><span data-stu-id="caa6a-150">Run the file SendPortGroups.exe.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="caa6a-151">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="caa6a-151">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="caa6a-152">以下 Windows PowerShell 脚本片段可用于演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="caa6a-152">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

```  
Function CreateSendPortGroup($Catalog, $strName)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  

   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

   #=== Create a new send port group and set its name ===#  

   $NewSendPortGroup = $Catalog.AddNewSendPortGroup()  
   $NewSendPortGroup.Name = $strName  

   #=== Persist new ports to the BizTalk Management database ===#  

   Write-Host Adding "`"$($NewSendPortGroup.Name)`"..."  
   $catalog.SaveChanges();  
   Write-Host "`r`nCreateSendPortGroup() completed."  
}  

Function DeleteSendPortGroup($Catalog,$strName)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  

   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered DeleteSendPortGroup:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();}  

   #=== Delete this sample's new send ports by name ===#  

   $NewSendPortGroup = $Catalog.SendPortGroups[$strName]  
   $Catalog.RemoveSendPortGroup($NewSendPortGroup)  

   #=== Persist changes to the BizTalk Management database ===#  

   Write-Host "Deleting `"$strName`"..."  
   $catalog.SaveChanges();  
   Write-Host "DeleteSendPortGroup() completed."  
}  

Function EnumerateSendPortGroups($Catalog)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  

   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered During Enumeration:`r`n"; $_; "`r`n"}  

   #=== Display all send port groups by name ===#  

   $count = 1  
   foreach ($group in $catalog.SendPortGroups)  
   {  
     Write-Host "$count. $($group.Name)"  
     $count++  
   }  

   Write-Host "`r`nEnumerateSendPortGroups() completed."  
}  

Function PromptForSendPort($Catalog)  
{  
   #=== Provide a list of the send ports for the user to make a selection ===#  

   Write-Host "Here is a list of send ports:`r`n"  
   $count = 1  
   foreach($sendport in $Catalog.SendPorts)  
   {  
      Write-Host ($Count). ($Sendport.Name)  
      $count++  
   }     

   Write-Host "`r`nChoose a port to add to the group by ordinal (ex. 1,2, etc): " -nonewline  
   $selection = read-host  
   $selection = $Catalog.SendPorts[([int]$selection)-1]  
   Write-Host $Selection.Name selected.  

   return $Selection.Name     
}  

Function AddSendPortToSendPortGroup($Catalog,$strPortName,$strGroupName)  
{  

   #=== Add the user's selected send port to the group ===#  

   #========================================================#  
   #=== Presently, we have to use WMI from PowerShell    ===#  
   #=== This is because the methods on the collections   ===#  
   #=== are marked internal. So unfortunately the        ===#  
   #=== following very straightforward code won't work.  ===#  
   #========================================================#  

   # $sendportgroup = $Catalog.SendPortGroups[$strName]  
   # $sendportgroup.SendPorts.Add($Catalog.SendPorts[$strPortName])  
   # $catalog.SaveChanges();  

   #============================================================================#  
   #=== Get the WMI send port group representation to look up DB and server. ===#     
   #=== Expecting only one to match the query in this example.               ===#  
   #============================================================================#  

   $WQL = "select * from MSBTS_SendPortGroup where Name='" + $strGroupName + "'"  
   $groupset = gwmi -query ($WQL) -namespace "root\MicrosoftBizTalkServer"  

   #=== Create a new MSBTS_SendPortGroup2SendPort instance to map the port to the group ===#     

   $group2port = [WMICLASS]"root\MicrosoftBizTalkServer:MSBTS_SendPortGroup2SendPort"  
   $newPortEntry = [WMI] $group2port.psbase.CreateInstance()  
   $newPortEntry.MgmtDbServerOverride = $groupset.MgmtDbServerOverride   
   $newPortEntry.MgmtDbNameOverride = $groupset.MgmtDbNameOverride  
   $newPortEntry.SendPortGroupName = $groupset.Name  
   $newPortEntry.SendPortName = $strPortName  
   Write-Host "Adding $strPortName to $($groupset.Name)"  

   #=== Persist changes to the BizTalk Management database ===#  

   #=== POWERSHELL V1 BUG WORKAROUND =============================#  
   #=== First method call on a non-cimv2 WMI object can fail.  ===#  
   #=== The workaround in PowerShell V1 is to call GetType()   ===#  
   #=== as the first method.                                   ===#   
   $ErrorActionPreference="silentlycontinue"                     
   trap {}  
   $newPortEntry.GetType()  
   #=== POWERSHELL V1 BUG WORKAROUND =============================#  

   $ErrorActionPreference="continue"                     
   [void] $newPortEntry.Put()  

   #=== Since we used WMI to update the BizTalk Management database, ===#  
   #=== refresh our BtsExplorerCatalog to have an updated DB view.   ===#  

   $Catalog.Refresh()  
   Write-Host "AddSendPortToSendPortGroup() completed."  
}  

Function DeleteSendPortFromSendPortGroup($Catalog, $strPortName, $strGroupName)  
{  
   #========================================================#  
   #=== Presently, we have to use WMI from PowerShell    ===#  
   #=== This is because the methods on the collections   ===#  
   #=== are marked internal. So unfortunately the        ===#  
   #=== following very straightforward code won't work.  ===#  
   #========================================================#  

   # $sendportgroup = $Catalog.SendPortGroups[$strGroupName]  
   # $sendportgroup.SendPorts.Remove($Catalog.SendPorts[$strPortName])  
   # $catalog.SaveChanges();  

   #============================================================================#  
   #=== Get the WMI send port to group instance and delete it.               ===#     
   #=== Expecting only one to match the query in this example.               ===#  
   #============================================================================#  

   $WQL = "select * from MSBTS_SendPortGroup2SendPort where " +   
          "SendPortName='" + $strPortName + "' and " +   
          "SendPortGroupName='" + $strGroupName + "'"  

   $groupset = gwmi -query ($WQL) -namespace "root\MicrosoftBizTalkServer"  

   write-host "Removing $strPortName from $strGroupName..."  
   $groupset.Delete();  

   #=== Since we used WMI to update the BizTalk Management database, ===#  
   #=== refresh our BtsExplorerCatalog to have an updated DB view.   ===#  

   $Catalog.Refresh()  
   Write-Host "DeleteSendPortFromSendPortGroup() completed."  
}  

#========================#  
#=== Main Script Body ===#  
#========================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "DATABASE=BizTalkMgmtDb;Integrated Security=SSPI;SERVER=."  

#=== Exercise the CreateSendPortGroup function to create a new send port group ===#  

$SendPortGroupName = "PowerShell Sample Send Port Group"  

Write-Host "`r`n============================="  
Write-Host "=== CreateSendPortGroup() ==="  
Write-Host "=============================`r`n"  
CreateSendPortGroup $Catalog $SendPortGroupName  

#=== Enumerate all send port groups to view the new one ===#  

Write-Host "`r`n================================="  
Write-Host "=== EnumerateSendPortGroups() ==="  
Write-Host "=================================`r`n"  
EnumerateSendPortGroups $Catalog  

#=== Add a send port to the group ===#  

Write-Host "`r`n===================================="  
Write-Host "=== AddSendPortToSendPortGroup() ==="  
Write-Host "====================================`r`n"  
$SendPortName = PromptForSendPort($Catalog)  
AddSendPortToSendPortGroup $Catalog $SendPortName $SendPortGroupName  

#=== Remove the send port from the group ===#  

Write-Host "`r`n========================================="  
Write-Host "=== DeleteSendPortFromSendPortGroup() ==="  
Write-Host "=========================================`r`n"  
DeleteSendPortFromSendPortGroup $Catalog $SendPortName $SendPortGroupName  

#=== Delete the group ===#  

Write-Host "`r`n============================="  
Write-Host "=== DeleteSendPortGroup() ==="  
Write-Host "=============================`r`n"  
DeleteSendPortGroup $Catalog $SendPortGroupName  

Write-Host  
```  

 <span data-ttu-id="caa6a-153">下面是从运行 Windows PowerShell 脚本示例的预期的示例输出。</span><span class="sxs-lookup"><span data-stu-id="caa6a-153">Here is example expected output from running the Windows PowerShell script sample.</span></span>  

```  
PS C:\> .\sendportgroups.ps1  

=============================  
=== CreateSendPortGroup() ===  
=============================  

Adding "PowerShell Sample Send Port Group"...  

CreateSendPortGroup() completed.  

=================================  
=== EnumerateSendPortGroups() ===  
=================================  

1. PowerShell Sample Send Port Group  

EnumerateSendPortGroups() completed.  

====================================  
=== AddSendPortToSendPortGroup() ===  
====================================  

Here is a list of send ports:  

1 . ResendPort  
2 . HelloWorldSendPort  
3 . ToCustomerSendPort  
4 . CBRUSSendPort  
5 . CBRCANSendPort  
6 . SendportCANOrders  

Choose a port to add to the group by ordinal (ex. 1,2, etc): 2  
HelloWorldSendPort selected.  
Adding HelloWorldSendPort to PowerShell Sample Send Port Group  
AddSendPortToSendPortGroup() completed.  

=========================================  
=== DeleteSendPortFromSendPortGroup() ===  
=========================================  

Removing HelloWorldSendPort from PowerShell Sample Send Port Group...  
DeleteSendPortFromSendPortGroup() completed.  

=============================  
=== DeleteSendPortGroup() ===  
=============================  

Deleting "PowerShell Sample Send Port Group"...  
DeleteSendPortGroup() completed.  
```  

## <a name="see-also"></a><span data-ttu-id="caa6a-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="caa6a-154">See Also</span></span>  
 [<span data-ttu-id="caa6a-155">Admin-ExplorerOM（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="caa6a-155">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)