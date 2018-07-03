---
title: DeleteParty （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- parties, examples
- deleting, parties
- examples, administering
- parties, deleting
- administering, examples
ms.assetid: 8161af7d-76ef-4df5-81c8-f0f5c81df9a8
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d6d488bf7431f805e8719e10fe17cef7d13fa4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982958"
---
# <a name="deleteparty-biztalk-server-sample"></a>DeleteParty （BizTalk Server 示例）
DeleteParty 示例演示如何删除指定参与方。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
> [!NOTE]
>  在删除参与方之前，必须先创建一个参与方。 执行操作的一种方法是运行[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)示例。  
  
## <a name="prerequisites"></a>必要條件  
  
- 您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。  
  
- Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。 有关详细信息请参阅：[检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例以 Microsoft Visual C# 编写，该示例使用 BizTalk 浏览器对象模型 (ExplorerOM) 中的对象执行下列操作：  
  
-   查询指定参与方。  
  
-   删除此参与方。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例将位于以下 SDK 位置：  
  
 \<*示例路径*\>\Admin\ExplorerOM\DeleteParty\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、DeleteParty.csproj、DeleteParty.sln 和 DeleteParty.cs|用于生成删除指定参与方的 Visual C# 命令行应用程序的项目、解决方案和源文件。|  
  
### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开 DeleteParty.sln 解决方案文件。  
  
2. 在“生成”  菜单上，单击“生成解决方案” 。  
  
### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1. 在命令窗口中，导航到下面的文件夹：  
  
    \<*示例路径*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\  
  
2. 运行 DeleteParty.exe 文件，并传递下面两个命令行参数之一：  
  
   - **\<** ***PartyName* \>。** 要删除的参与方的名称。 如果参与方名称包含空格，则将该名称置于引号中。  
  
   - **/?.** 显示帮助。  
  
     例如：  
  
   ```  
   DeleteParty "My Party #3"  
   ```  
  
    -或-  
  
   ```  
   DeleteParty /?  
   ```  
  
## <a name="windows-powershell-script-example"></a>Windows Powershell 脚本示例  
 以下 Windows PowerShell 脚本片段可用于演示的相同功能**ExplorerOM**类：  
  
```  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=======================================#  
#=== If no party name is specified   ===#  
#=== just list the parties.          ===#  
#=======================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`nNo party name provided for delete operation.`r`n`r`nListing Parties on local Biztalk Server:  
  
  $Catalog.Parties | Format-List Name  
}  
  
#==========================================#  
#=== Delete the specified party by name ===#  
#==========================================#  
  
else  
{  
  $party = $Catalog.Parties[$args[0]]  
  Write-Host `r`nRemoving Party named `"($args[0])`"`r`n  
  $catalog.RemoveParty($party)  
  $catalog.SaveChanges()  
}  
```  
  
 该脚本示例希望将单个参与方名称作为命令行参数来传递。  它通过名称来查找该参与方，并尝试将其删除。  如果没有传递命令行参数给脚本，则该脚本会列出本地 Biztalk Server 上的所有参与方。 下面是该脚本的示例输出：  
  
```  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party3  
  
Name : Party2  
  
PS C:\> .\DeletePart.ps1 Party3  
  
Removing Party named " Party3 "  
  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party2  
  
```  
  
## <a name="see-also"></a>请参阅  
 [Admin-ExplorerOM（BizTalk Server 示例文件夹）](../core/admin-explorerom-biztalk-server-samples-folder.md)