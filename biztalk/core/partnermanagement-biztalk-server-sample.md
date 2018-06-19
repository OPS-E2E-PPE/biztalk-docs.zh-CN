---
title: PartnerManagement （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83e2a84f-ab25-4a7c-b8d7-0ba2dfa93095
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ffc9e84e8c31ed1e1feb4c768498e817ad474c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973651"
---
# <a name="partnermanagement-biztalk-server-sample"></a><span data-ttu-id="4a967-102">PartnerManagement（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="4a967-102">PartnerManagement (BizTalk Server Sample)</span></span>
<span data-ttu-id="4a967-103">PartnerManagement 示例演示如何管理中的各方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境使用**ExplorerOM**管理对象。</span><span class="sxs-lookup"><span data-stu-id="4a967-103">The PartnerManagement sample demonstrates how to manage parties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by using the **ExplorerOM** administration objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a967-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="4a967-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="4a967-105">您必须具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理权限才能使用此示例中的管理对象。</span><span class="sxs-lookup"><span data-stu-id="4a967-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="4a967-106">Windows PowerShell 脚本需要 Windows PowerShell 执行策略以允许脚本执行。</span><span class="sxs-lookup"><span data-stu-id="4a967-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="4a967-107">有关详细信息，请参阅 [检查执行策略](http://go.microsoft.com/fwlink/?LinkId=128930)。</span><span class="sxs-lookup"><span data-stu-id="4a967-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="4a967-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="4a967-108">What This Sample Does</span></span>  
 <span data-ttu-id="4a967-109">此示例演示如何使用中的管理类**Microsoft.BizTalk.ExplorerOM**命名空间以管理方。</span><span class="sxs-lookup"><span data-stu-id="4a967-109">This sample demonstrates using the administrative classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage parties.</span></span> <span data-ttu-id="4a967-110">参与方代表贸易合作伙伴，或业务流程可与之交互的后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a967-110">Parties represent trading partners or back-end applications with which a business process can interact.</span></span> <span data-ttu-id="4a967-111">有关方一般情况下，请参阅的文档[方](../core/parties.md)或[角色链接和服务链接角色](../core/role-links-and-service-link-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="4a967-111">For more information about parties in general, see the documentation for [Parties](../core/parties.md) or [Role Links and Service Link Roles](../core/role-links-and-service-link-roles.md).</span></span> <span data-ttu-id="4a967-112">本示例是使用 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 编写的。</span><span class="sxs-lookup"><span data-stu-id="4a967-112">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="4a967-113">本主题中还包含 Windows PowerShell 示例脚本。</span><span class="sxs-lookup"><span data-stu-id="4a967-113">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="4a967-114">本示例将演示以下操作：</span><span class="sxs-lookup"><span data-stu-id="4a967-114">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="4a967-115">使用自定义或标准别名创建新的参与方，并向此参与方中添加现有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口。</span><span class="sxs-lookup"><span data-stu-id="4a967-115">Creating a new party with a custom or standard alias and adding existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send ports to the party.</span></span>  
  
-   <span data-ttu-id="4a967-116">向 BizTalk Server 上的现有角色链接登记新创建的参与方。</span><span class="sxs-lookup"><span data-stu-id="4a967-116">Enlisting the new party with an existing role link on the BizTalk server.</span></span>  
  
-   <span data-ttu-id="4a967-117">注销新创建的参与方。</span><span class="sxs-lookup"><span data-stu-id="4a967-117">Un-enlisting the new party.</span></span>  
  
-   <span data-ttu-id="4a967-118">删除新创建的参与方。</span><span class="sxs-lookup"><span data-stu-id="4a967-118">Deleting the new party.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4a967-119">本示例的所在位置</span><span class="sxs-lookup"><span data-stu-id="4a967-119">Where To Find This Sample</span></span>  
 <span data-ttu-id="4a967-120">本示例位于以下 SDK 位置中：</span><span class="sxs-lookup"><span data-stu-id="4a967-120">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="4a967-121">\<*示例路径*\>\Admin\ExplorerOM\PartnerManagement</span><span class="sxs-lookup"><span data-stu-id="4a967-121">\<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement</span></span>  
  
 <span data-ttu-id="4a967-122">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="4a967-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="4a967-123">文件</span><span class="sxs-lookup"><span data-stu-id="4a967-123">File(s)</span></span>|<span data-ttu-id="4a967-124">Description</span><span class="sxs-lookup"><span data-stu-id="4a967-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a967-125">PartnerManagement.cs</span><span class="sxs-lookup"><span data-stu-id="4a967-125">PartnerManagement.cs</span></span>|<span data-ttu-id="4a967-126">本示例中演示的操作所需的 [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 源文件。</span><span class="sxs-lookup"><span data-stu-id="4a967-126">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="4a967-127">PartnerManagement.sln 和 PartnerManagement.csproj</span><span class="sxs-lookup"><span data-stu-id="4a967-127">PartnerManagement.sln and PartnerManagement.csproj</span></span>|<span data-ttu-id="4a967-128">示例的解决方案文件和项目文件。</span><span class="sxs-lookup"><span data-stu-id="4a967-128">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="4a967-129">生成并运行本示例</span><span class="sxs-lookup"><span data-stu-id="4a967-129">Building and Running This Sample</span></span>  
 <span data-ttu-id="4a967-130">在生成本示例之前，您需要进行四次代码修改，以便为 BizTalk Server 自定义本示例。</span><span class="sxs-lookup"><span data-stu-id="4a967-130">Before you build the sample, you need to make four code modifications to customize the sample for the BizTalk server.</span></span> <span data-ttu-id="4a967-131">此操作是必须的，因为该示例对与参与方相关的发送端口使用任意名称，并且在登记时也使用任意角色名称。</span><span class="sxs-lookup"><span data-stu-id="4a967-131">This is necessary because the sample uses arbitrary names for send ports associated with the party and an arbitrary role name for the enlistment.</span></span> <span data-ttu-id="4a967-132">因此，您需要为此示例提供有效名称。</span><span class="sxs-lookup"><span data-stu-id="4a967-132">Therefore you need to provide valid names to the sample.</span></span> <span data-ttu-id="4a967-133">为了演示此示例，本主题介绍首先生成从下列目录 PartyResolution 示例： \<*示例路径*\>\Orchestrations\PartyResolution。</span><span class="sxs-lookup"><span data-stu-id="4a967-133">To demonstrate this sample, this topic describes first building the PartyResolution sample from the following directory: \<*Samples Path*\>\Orchestrations\PartyResolution.</span></span> <span data-ttu-id="4a967-134">此方法用于确保在 BizTalk Server 上存在有效的角色名称和发送端口名称，以演示示例过程。</span><span class="sxs-lookup"><span data-stu-id="4a967-134">This approach is used to make sure a valid role name and send port names are present on the BizTalk server to demonstrate the sample procedures.</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="4a967-135">生成示例</span><span class="sxs-lookup"><span data-stu-id="4a967-135">To build this sample</span></span>  
  
1.  <span data-ttu-id="4a967-136">首先，确保已生成并已初始化 PartyResolution 示例，以便此示例能够使用有效的角色名称和发送端口名称。</span><span class="sxs-lookup"><span data-stu-id="4a967-136">First make sure the PartyResolution sample has been built and initialized so that a valid role name and send port names can be used by the sample.</span></span> <span data-ttu-id="4a967-137">在"构建并初始化此示例"部分中介绍了此[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="4a967-137">This is documented in the section entitled “Building and Initializing This Sample” in  [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  
  
2.  <span data-ttu-id="4a967-138">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中打开 PartnerManagement.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="4a967-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file PartnerManagement.sln.</span></span>  
  
3.  <span data-ttu-id="4a967-139">在解决方案资源管理器中，打开源文件 PartnerManagement.cs。</span><span class="sxs-lookup"><span data-stu-id="4a967-139">In Solution Explorer, open the source file PartnerManagement.cs.</span></span>  
  
4.  <span data-ttu-id="4a967-140">向下滚动到名为函数**CreateParty**和插入两个发送端口名称从 PartyResolution 示例或使用 BizTalk 服务器环境中的有效名称。</span><span class="sxs-lookup"><span data-stu-id="4a967-140">Scroll down into the function named **CreateParty** and insert the two send port names from the PartyResolution sample or use valid names from the BizTalk server environment.</span></span> <span data-ttu-id="4a967-141">以下代码示例演示如何使用来自 PartyResolution 示例的发送端口进行更改。</span><span class="sxs-lookup"><span data-stu-id="4a967-141">The following code example demonstrates the change using the send ports from the PartyResolution sample.</span></span>  
  
    ```  
    // Replacing arbitrary send port names with PartyResolution send port names ===  
  
    //            myParty.SendPorts.Add(catalog.SendPorts["NormalDelivery"]);  
    //            myParty.SendPorts.Add(catalog.SendPorts["ExpressDelivery"]);  
                myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency1"]);  
                myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency2"]);  
  
    ```  
  
5.  <span data-ttu-id="4a967-142">向下滚动到名为函数**EnlistParty**并更改 foreach 循环，以使它搜索名为"ShipmentRole"的角色的供应商程序集用于登记。</span><span class="sxs-lookup"><span data-stu-id="4a967-142">Scroll down into the function named **EnlistParty** and change the foreach loop so that it searches the Supplier assembly for a role named “ShipmentRole” to use with the enlistment.</span></span> <span data-ttu-id="4a967-143">以下代码示例演示如何改为使用来自 PartyResolution 示例的 ShipmentRole。</span><span class="sxs-lookup"><span data-stu-id="4a967-143">The following code example demonstrates the change to use the ShipmentRole from the PartyResolution sample.</span></span>  
  
    ```  
                // Search for the “Shipmentrole” instead of “shipperRole”  
                Role svcRole = null;  
    //===       foreach (Role role in catalog.Assemblies[0].Roles)  
                foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
                {  
    //===          if (role.Name == "ShipperRole")  
                   if (role.Name == "ShipmentRole")  
                   {  
                      svcRole = role;  
                      break;  
                   }  
                }  
  
    ```  
  
6.  <span data-ttu-id="4a967-144">向下滚动到名为函数**UnenlistParty**和更改 foreach 循环要搜索 ShipmentRole 的供应商程序集。</span><span class="sxs-lookup"><span data-stu-id="4a967-144">Scroll down into the function named **UnenlistParty** and change the foreach loop to search the Supplier assembly for the ShipmentRole.</span></span> <span data-ttu-id="4a967-145">以下代码示例演示了此更改。</span><span class="sxs-lookup"><span data-stu-id="4a967-145">The following code example demonstrates this change.</span></span>  
  
    ```  
                // Search for the “ShipmentRole” instead of “shipperRole”  
                Role svcRole = null;  
    //===       foreach (Role role in catalog.Assemblies[0].Roles)  
                foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
                {  
    //===          if (role.Name == "ShipperRole")  
                   if (role.Name == "ShipmentRole")  
                   {  
                      svcRole = role;  
                      break;  
                   }  
                }  
  
    ```  
  
7.  <span data-ttu-id="4a967-146">使用 ShipmentRole 创建并登记新参与方之后，此示例用于立即注销此参与方并将其删除。</span><span class="sxs-lookup"><span data-stu-id="4a967-146">After creating and enlisting the new party with the ShipmentRole, the sample is designed to immediately un-enlist the party and delete it.</span></span> <span data-ttu-id="4a967-147">将以下代码更改添加到主过程，以暂停过程执行，并允许您在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中查看为新参与方创建的登记。</span><span class="sxs-lookup"><span data-stu-id="4a967-147">Add the following code change to the main procedure to pause execution and allow you to view the created enlistment for the new party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
       CreateParty();     
       EnlistParty();     
  
       Console.WriteLine("\nNew Party created and enlisted.\n\nPress <Enter> to unenlist and delete.\n");  
       Console.ReadLine();  
  
       UnenlistParty();   
       DeleteParty();  
    }  
  
    ```  
  
8.  <span data-ttu-id="4a967-148">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="4a967-148">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="4a967-149">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="4a967-149">To run this sample</span></span>  
  
1.  <span data-ttu-id="4a967-150">打开命令窗口并导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="4a967-150">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="4a967-151">\<*示例路径*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="4a967-151">\<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug</span></span>  
  
2.  <span data-ttu-id="4a967-152">运行文件 PartnerManagement.exe。</span><span class="sxs-lookup"><span data-stu-id="4a967-152">Run the file PartnerManagement.exe.</span></span>  
  
3.  <span data-ttu-id="4a967-153">当此示例显示创建并登记新的参与方的消息时，打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台和视图，以及名为新的当事方**FedEx**下**方**节点。</span><span class="sxs-lookup"><span data-stu-id="4a967-153">When the sample displays the message that the new party is created and enlisted, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and view the new party named **FedEx** under the **Parties** node.</span></span>  
  
4.  <span data-ttu-id="4a967-154">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，导航到树视图**ShipmentRole**下**Applications\BizTalk 应用程序 1\Role 链接**。</span><span class="sxs-lookup"><span data-stu-id="4a967-154">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, navigate the tree view to the **ShipmentRole** under **Applications\BizTalk Application 1\Role Links**.</span></span> <span data-ttu-id="4a967-155">双击**ShipmentRole** ，并注意**ShipmentAgency1**映射到**SupplierAdvice**操作和**ShipmentAgency2**映射到**SupplierOrder**中登记的操作。</span><span class="sxs-lookup"><span data-stu-id="4a967-155">Double-click **ShipmentRole** and notice **ShipmentAgency1** mapped to the **SupplierAdvice** operation and **ShipmentAgency2** mapped to the **SupplierOrder** operation in the enlistment.</span></span>  
  
5.  <span data-ttu-id="4a967-156">在命令窗口中，按 Enter 以允许示例注销并删除此新参与方。</span><span class="sxs-lookup"><span data-stu-id="4a967-156">In the command window, press ENTER to allow the sample to un-enlist and delete the new party.</span></span>  
  
6.  <span data-ttu-id="4a967-157">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，验证当事方是否取消登记从**ShipmentRole**和删除从**方**节点。</span><span class="sxs-lookup"><span data-stu-id="4a967-157">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, verify the party was un-enlisted from the **ShipmentRole** and deleted from the **Parties** node.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="4a967-158">Windows Powershell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="4a967-158">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="4a967-159">可以使用以下 Windows PowerShell 脚本示例来演示的相同功能**ExplorerOM**类：</span><span class="sxs-lookup"><span data-stu-id="4a967-159">The following Windows PowerShell script example can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#===============================================================#  
#===                                                         ===#  
#=== Create a new party named "FedEx" as an example.         ===#  
#===                                                         ===#  
#=== Two Shipment agency send ports from the PartyResolution ===#  
#=== sample will be added to the party.                      ===#  
#===                                                         ===#  
#===============================================================#  
Function CreateParty  
{  
  #=== Create a party =====================#  
  $myParty = $Catalog.AddNewParty()  
  $myParty.Name = "FedEx"  
  
  #=== create a standard alias ==========================#  
  $standardAlias = $myParty.AddNewAlias()  
  $standardAlias.Name = "D-U-N-S (Dun & Bradstreet)"  
  $standardAlias.Value = "Value1"  
  
  #=== Create a custom alias ==================#  
  $customAlias = $myParty.AddNewAlias()  
  $customAlias.Name = "Telephone"  
  $customAlias.Qualifier = "100"  
  $customAlias.Value = "4255550234"  
  
  #=== Add party send ports =====================================================#  
  
  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]  
  
  $sendport1 = $Catalog.SendPorts["SP_FilesToShipmentAgency1"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport1)  
  
  $sendport2 = $Catalog.SendPorts["SP_FilesToShipmentAgency2"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport2)  
  
  #=== Specify a signature certificate, make sure the certificate is available ===#  
  #=== in the AddressBook store of the Local Machine                           ===#  
  
  foreach ($certificate in $Catalog.Certificates)  
  {  
    if ($certificate.ShortName -eq "BR, Certisign Certificadora Digital Ltda., Certisign - Autoridade Certificadora - AC2")  
    {  
      $myParty.SignatureCert = $certificate  
    }  
  }  
  
  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Delete the party named "FedEx"                          ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteParty  
{  
  $Catalog.RemoveParty($Catalog.Parties["FedEx"])  
  
  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Enlist the "FedEx" party with the "ShipmentRole"        ===#  
#===                                                         ===#  
#===============================================================#  
Function EnlistParty  
{  
  $myParty = $Catalog.Parties["FedEx"]  
  
  #=== Get the "ShipmentRole" in the Supplier assembly.        ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  
  
  #=== Enlist the party under the shipper role ===#  
  $enlistedParty = $svcRole.AddNewEnlistedParty($myParty)  
  
  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]   
  
  #===============================================================#  
  #=== Example port to be used for the role's "SupplierAdvice" ===#  
  #=== operation.                                              ===#  
  #=== Using the first send port added to the new party which  ===#  
  #=== is "SP_FilesToShipmentAgency1" at index 0 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[0].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,0)  
  
  #===============================================================#  
  #=== Example port to be used for the role's "SupplierOrder"  ===#  
  #=== operation.                                              ===#  
  #=== Using the second send port added to the new party which ===#  
  #=== is "SP_FilesToShipmentAgency2" at index 1 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[1].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,1)  
  
  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Unenlist the "FedEx" party from the ShipmentRole        ===#  
#===                                                         ===#  
#===============================================================#  
Function UnenlistParty  
{  
  #=== Get the "ShipmentRole" from the Supplier assembly. ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  
  
  #=== Remove the "FedEx" party ===#  
  foreach ($enlistedparty in $svcRole.EnlistedParties)  
  {  
    if ($enlistedparty.Party.Name -eq "FedEx")  
    {  
      $svcRole.RemoveEnlistedParty($enlistedparty)  
      break  
    }  
  }  
  
  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== This sample expects the PartyResolution sample to be built and deployed  ===#  
#=== to the BizTalk Server.                                                   ===#  
  
write-host `r`nMake sure the "PartyResolution" sample application from the Orchestrations   
write-host sample directory is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  
  
$SupplierAssembly = $Catalog.Assemblies["Supplier"]  
  
#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to unenlist,  ===#  
#=== and delete the party.                                      ===#  
#==================================================================#  
  
$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the party...`r`n"  
  $Catalog.DiscardChanges()  
}  
  
CreateParty  
EnlistParty  
  
if ($Script:NoExceptionOccurred)  
{  
  Write-Host "`r`nExample Party `"FedEx`" should be created and enlisted with the `"ShipmentRole`".`r`n"  
  Write-Host You can view the results in the BizTalk Server Administration console.`r`n  
  Write-Host "Press <Enter> to unenlist and delete...`r`n"  
  Read-Host  
}  
  
UnenlistParty  
DeleteParty  
  
```  
  
 <span data-ttu-id="4a967-160">以下是运行 PowerShell 示例脚本的示例输出。</span><span class="sxs-lookup"><span data-stu-id="4a967-160">Here is example output from running the PowerShell example script.</span></span> <span data-ttu-id="4a967-161">如果脚本运行失败，请确保已根据本主题前面部分中的要求说明启用 PowerShell 脚本功能。</span><span class="sxs-lookup"><span data-stu-id="4a967-161">If the script fails to run, make sure PowerShell scripting is enabled according to the requirements note at the top of this topic.</span></span>  
  
```  
PS C:\> .\PartnerManagement.ps1  
  
Make sure the PartyResolution sample application from the Orchestrations  
sample directory is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  
  
Example Party "FedEx" should be created and enlisted with the "ShipmentRole".  
  
You can view the results in the BizTalk Server Administration console.  
  
Press <Enter> to unenlist and delete...  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a967-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a967-162">See Also</span></span>  
 <span data-ttu-id="4a967-163">[方](../core/parties.md) </span><span class="sxs-lookup"><span data-stu-id="4a967-163">[Parties](../core/parties.md) </span></span>  
 <span data-ttu-id="4a967-164">[角色链接和服务链接角色](../core/role-links-and-service-link-roles.md) </span><span class="sxs-lookup"><span data-stu-id="4a967-164">[Role Links and Service Link Roles](../core/role-links-and-service-link-roles.md) </span></span>  
 [<span data-ttu-id="4a967-165">Admin（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="4a967-165">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)