---
title: 如何导出 EDI-AS2 解决方案的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 856ab630-66c4-4496-884a-fdbe641143c5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36bd9c265d28555c40f84f1728fd28846fbd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012326"
---
# <a name="how-to-export-bindings-for-an-edi-as2-solution"></a><span data-ttu-id="51cd2-102">如何导出 EDI-AS2 解决方案的绑定</span><span class="sxs-lookup"><span data-stu-id="51cd2-102">How to Export Bindings for an EDI-AS2 Solution</span></span>
<span data-ttu-id="51cd2-103">本主题介绍如何从设置为 EDI 和/或 AS2 解决方案的计算机中导出配置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-103">This topic describes how to export the configuration from a computer set up as an EDI and/or AS2 solution.</span></span> <span data-ttu-id="51cd2-104">这样，您可以以自动方式在其他计算机上设置相同配置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-104">This enables you to set up the same configuration on another computer in an automated fashion.</span></span> <span data-ttu-id="51cd2-105">您可以从应用程序、组或程序集导出绑定。</span><span class="sxs-lookup"><span data-stu-id="51cd2-105">You can export the bindings from an application, group, or assembly.</span></span>  
  
 <span data-ttu-id="51cd2-106">您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建绑定文件。</span><span class="sxs-lookup"><span data-stu-id="51cd2-106">You create a binding file from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="51cd2-107">此 .xml 绑定文件包含与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置相关的所有信息。</span><span class="sxs-lookup"><span data-stu-id="51cd2-107">The .xml binding file contains all information pertinent to your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration.</span></span> <span data-ttu-id="51cd2-108">其中包括所有 EDI 和 AS2 配置属性，但某些安全信息除外。</span><span class="sxs-lookup"><span data-stu-id="51cd2-108">This includes all EDI and AS2 configuration properties, with the exception of certain security information.</span></span> <span data-ttu-id="51cd2-109">有关绑定文件 （包括 EDI 和 AS2 节点） 中的节点的详细信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。</span><span class="sxs-lookup"><span data-stu-id="51cd2-109">For detailed information about the nodes in a binding file (including EDI and AS2 nodes), see [Structure of a Binding File](../core/structure-of-a-binding-file.md).</span></span> <span data-ttu-id="51cd2-110">有关 EDI/AS2 绑定的常规信息，请参阅下面的“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 绑定文件中的 EDI 和 AS2 节点”。</span><span class="sxs-lookup"><span data-stu-id="51cd2-110">For general information about the EDI/AS2 bindings, see "EDI and AS2 Nodes in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Binding File" below.</span></span>  
  
 <span data-ttu-id="51cd2-111">您还可以在使用 .msi 文件导出应用程序时导出绑定。</span><span class="sxs-lookup"><span data-stu-id="51cd2-111">You can also export bindings as part of exporting an application using an .msi file.</span></span> <span data-ttu-id="51cd2-112">有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="51cd2-112">For more information, see the [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span> <span data-ttu-id="51cd2-113">还可以用 BTSTask 命令导出和导入绑定。</span><span class="sxs-lookup"><span data-stu-id="51cd2-113">Or you can use the BTSTask command to export and import bindings.</span></span> <span data-ttu-id="51cd2-114">有关 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="51cd2-114">For more information about BTSTask, see [BTSTask Command-Line Reference](../core/btstask-command-line-reference.md).</span></span>  
  
 <span data-ttu-id="51cd2-115">**导出绑定**</span><span class="sxs-lookup"><span data-stu-id="51cd2-115">**Exporting Bindings**</span></span>  
  
 <span data-ttu-id="51cd2-116">导出配置时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将自动导出所有绑定参与方的 EDI 属性，以及其他参与方信息。</span><span class="sxs-lookup"><span data-stu-id="51cd2-116">When you export the configuration, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will automatically export the EDI Properties, and other party information, of all bound parties.</span></span> <span data-ttu-id="51cd2-117">如果激活导出全局参与方信息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 还将导出未绑定到业务流程的参与方的属性以及全局 EDI 属性。</span><span class="sxs-lookup"><span data-stu-id="51cd2-117">If you activate the exporting of global party information, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also export properties for parties that are not bound to an orchestration, and global EDI properties.</span></span> <span data-ttu-id="51cd2-118">您可以按如下三种方式导出全局参与方信息：</span><span class="sxs-lookup"><span data-stu-id="51cd2-118">You can export global party information in three ways:</span></span>  
  
- <span data-ttu-id="51cd2-119">通过选中“导出绑定”对话框中的“导出全局参与方信息”属性。</span><span class="sxs-lookup"><span data-stu-id="51cd2-119">By checking the Export Global Party Information property in the Export Bindings dialog box.</span></span>  
  
- <span data-ttu-id="51cd2-120">通过选中导出 MSI 文件向导的“选择资源”窗格中的“全局参与方”复选框。</span><span class="sxs-lookup"><span data-stu-id="51cd2-120">By checking the Global Parties checkbox in the Select Resources pane of the Export MSI File Wizard.</span></span>  
  
- <span data-ttu-id="51cd2-121">通过使用 BTSTask 命令行工具中的 GlobalParties 开关，如下所示：</span><span class="sxs-lookup"><span data-stu-id="51cd2-121">By using the GlobalParties switch in the BTSTask command line tool, as follows:</span></span>  
  
  ```  
  BTSTask ExportBindings -Destination:value ((([-ApplicationName:value] | [-AssemblyName:value]) [-GlobalParties]) | [-GroupLevel])  
  ```  
  
  <span data-ttu-id="51cd2-122">出于安全原因，当您导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会从文件删除绑定的密码。</span><span class="sxs-lookup"><span data-stu-id="51cd2-122">For security reasons, when you export a binding file, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] removes the passwords for the bindings from the file.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="51cd2-123"> 从 EDIFACT 属性和 X12 中的 ISA1 和 ISA2、 ISA3，和 ISA4 字段中删除 UNB6.1 和 UNB6.2 字段属性。</span><span class="sxs-lookup"><span data-stu-id="51cd2-123"> removes UNB6.1 and UNB6.2 fields from EDIFACT Properties, and ISA1, ISA2, ISA3, and ISA4 fields from X12 Properties.</span></span>  
  
  <span data-ttu-id="51cd2-124">除使用导出绑定、导出应用程序或 BTSTask 命令之外，您还可以手动创建 XML 绑定文件。</span><span class="sxs-lookup"><span data-stu-id="51cd2-124">In addition to using the export-bindings, export-application, or BTSTask commands, you can create an XML binding file manually.</span></span> <span data-ttu-id="51cd2-125">这样，您可以从业务线应用程序导出参与方和 EDI 设置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-125">By doing so, you can export party and EDI settings from a line-of-business application.</span></span> <span data-ttu-id="51cd2-126">然后，您可以使用导入绑定命令或 BTSTask 命令导入绑定。</span><span class="sxs-lookup"><span data-stu-id="51cd2-126">You could then import the bindings using the import-bindings command or the BTSTask command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51cd2-127">必要條件</span><span class="sxs-lookup"><span data-stu-id="51cd2-127">Prerequisites</span></span>  
 <span data-ttu-id="51cd2-128">您必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员身份帐户登录。</span><span class="sxs-lookup"><span data-stu-id="51cd2-128">You must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="51cd2-129">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“部署和管理 BizTalk 应用程序所需的权限”。</span><span class="sxs-lookup"><span data-stu-id="51cd2-129">For more information, see "Permissions Required for Deploying and Managing a BizTalk Application" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
### <a name="exporting-the-configuration-into-a-binding-file"></a><span data-ttu-id="51cd2-130">将配置导出到绑定文件</span><span class="sxs-lookup"><span data-stu-id="51cd2-130">Exporting the Configuration into a Binding File</span></span>  
  
1. <span data-ttu-id="51cd2-131">在要从中导出配置的计算机上，打开“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台”。</span><span class="sxs-lookup"><span data-stu-id="51cd2-131">On the computer that you want to export the configuration from, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2. <span data-ttu-id="51cd2-132">右键单击 BizTalk 应用程序想要复制其配置，请指向**导出**，然后单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="51cd2-132">Right-click the BizTalk Application that you want to copy the configuration from, point to **Export**, and then click **Bindings**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="51cd2-133">您还可以使用 BTSTask 实用工具导出或导入配置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-133">You can also use the BTSTask utility to export or import the configuration.</span></span>  
  
3. <span data-ttu-id="51cd2-134">选择导出选项，选择从当前应用程序或组导出，或者导出程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="51cd2-134">Select the export option, selecting to export from the current application or group, or exporting bindings for an assembly.</span></span>  
  
4. <span data-ttu-id="51cd2-135">如果你想要导出所有参与方，并且其非敏感属性，即使业务流程未绑定到它们，再单击**导出全局参与方信息**。</span><span class="sxs-lookup"><span data-stu-id="51cd2-135">If you want to export all parties and their non-sensitive properties, even if an orchestration is not bound to them, click **Export Global Party information**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="51cd2-136">如果不单击**导出全局参与方信息**，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将导出所有参与方绑定到业务流程，到绑定文件的属性。</span><span class="sxs-lookup"><span data-stu-id="51cd2-136">If you do not click **Export Global Party information**, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will export properties for any parties that are bound to an orchestration, into the binding file.</span></span> <span data-ttu-id="51cd2-137">但是，它将不会导出所有参与方的未绑定到业务流程，除非您单击**导出全局参与方信息**。</span><span class="sxs-lookup"><span data-stu-id="51cd2-137">However, it will not export any parties that are not bound to an orchestration, unless you click **Export Global Party information**.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="51cd2-138">生成的绑定文件时**导出全局参与方信息**选择属性，则将包括的计算机上定义的所有参与方的配置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-138">The binding file generated while the **Export Global Party information** property is selected will include the configuration of all parties defined on the computer.</span></span> <span data-ttu-id="51cd2-139">无法导出计算机上定义的完整参与方集合子集的配置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-139">It is not possible to export the configuration of a subset of the complete set of parties defined on a computer.</span></span>  
  
5. <span data-ttu-id="51cd2-140">单击**确定**导出绑定。</span><span class="sxs-lookup"><span data-stu-id="51cd2-140">Click **OK** to export the bindings.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="51cd2-141"> 将不会导出任何 EDI 保密字段，例如密码或安全/身份验证信息。</span><span class="sxs-lookup"><span data-stu-id="51cd2-141"> will not export any EDI sensitive fields, such as passwords or security/authentication information.</span></span> <span data-ttu-id="51cd2-142">对于任何 EDI 保密字段，BizTalk Server 将导出一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="51cd2-142">It will export a blank string for any EDI sensitive field.</span></span> <span data-ttu-id="51cd2-143">将绑定导入到其他计算机中后，必须手动设置 EDI 保密字段的值。</span><span class="sxs-lookup"><span data-stu-id="51cd2-143">After importing the bindings onto another computer, you must manually set the values for EDI sensitive fields.</span></span>  
  
6. <span data-ttu-id="51cd2-144">手动记下所有 EDI 保密字段（如密码或安全/身份验证信息），以便稍后在要向其导入绑定的计算机上进行设置。</span><span class="sxs-lookup"><span data-stu-id="51cd2-144">Manually note any EDI sensitive fields, such as passwords or security/authentication information, for later setting on the computer that you import the bindings onto.</span></span>  
  
## <a name="edi-and-as2-nodes-in-the-biztalk-server-binding-file"></a><span data-ttu-id="51cd2-145">BizTalk Server 绑定文件中的 EDI 和 AS2 节点</span><span class="sxs-lookup"><span data-stu-id="51cd2-145">EDI and AS2 Nodes in the BizTalk Server Binding File</span></span>  
 <span data-ttu-id="51cd2-146">如果导出您的配置**导出全局参与方信息**属性处于选中状态，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成具有下列节点的绑定文件：</span><span class="sxs-lookup"><span data-stu-id="51cd2-146">If you export your configuration with the **Export Global Party information** property selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a binding file that has that following nodes:</span></span>  
  
```  
EdiData  
   PartyEDIProperties  
      PartnerAgreement  
         Contacts  
      PartnerEdifact  
         PartnerEdifactReceiverGroups  
         PartnerEdifactSenderGroups  
      PartnerAckValidation  
      PartnerX12  
      PartnerX12ReceiverGroups  
      PartnerX12SenderGroups  
      PartnerBatchUpdatable  
      PartnerAS2CommonUpdatable  
      PartnerAS2  
```  
  
 <span data-ttu-id="51cd2-147">EDI 全局属性将在下列节点中添加到绑定文件中。</span><span class="sxs-lookup"><span data-stu-id="51cd2-147">EDI global properties will be added to the binding file in the following nodes.</span></span>  
  
```  
EDIGlobalProperties  
   EDIGlobalProperties  
      GlobalCommon  
      GlobalEdiFact  
      GlobalX12  
```  
  
 <span data-ttu-id="51cd2-148">EDI 和 AS2 节点将被添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 绑定文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="51cd2-148">EDI and AS2 nodes are added to the end of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] binding file.</span></span> <span data-ttu-id="51cd2-149">EdiData 节点将被添加到“参与方集合”节点下的“参与方”子节点；而 EdiGlobalProperties 节点将被添加到“参与方集合”节点之后，且其级别与“参与方集合”节点的级别相同。</span><span class="sxs-lookup"><span data-stu-id="51cd2-149">The EdiData node is added to the Party subnode under the Party Collection node, and the EdiGlobalProperties node is added after, and at the same level as, the Party Collection node.</span></span> <span data-ttu-id="51cd2-150">有关 BizTalk 绑定文件中的 EDI 和 AS2 节点的详细信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。</span><span class="sxs-lookup"><span data-stu-id="51cd2-150">For more information about the EDI and AS2 nodes in the BizTalk binding file, see [Structure of a Binding File](../core/structure-of-a-binding-file.md).</span></span>  
  
 <span data-ttu-id="51cd2-151">EdiData 节点是可选的。</span><span class="sxs-lookup"><span data-stu-id="51cd2-151">The EdiData node is optional.</span></span> <span data-ttu-id="51cd2-152">但是，如果存在 EdiData 节点，则 EdiData 下的子节点是必需的。</span><span class="sxs-lookup"><span data-stu-id="51cd2-152">However, if the EdiData node is present, the subnodes under EdiData are required.</span></span> <span data-ttu-id="51cd2-153">同样，EdiGlobalProperties 节点也是可选的；但是，如果存在 EdiGlobalProperties 节点，则该节点下的子节点是必需的。</span><span class="sxs-lookup"><span data-stu-id="51cd2-153">Likewise, the EdiGlobalProperties node is optional; however, if the EdiGlobalProperties node is present, the subnodes under it are required.</span></span>  
  
 <span data-ttu-id="51cd2-154">EDI 和 AS2 绑定文件节点不与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的合作伙伴协议管理器的属性页直接对应。</span><span class="sxs-lookup"><span data-stu-id="51cd2-154">EDI and AS2 binding file nodes do not correspond directly to the property pages in the Partner Agreement Manager in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="51cd2-155">某些 EDI 和 AS2 绑定文件节点包含适用于发送方角色和接收方角色的属性。</span><span class="sxs-lookup"><span data-stu-id="51cd2-155">Some EDI and AS2 binding file nodes include properties used for sender roles and properties used for receiver roles.</span></span> <span data-ttu-id="51cd2-156">角色是由节点中的 IsSender 属性指示的。</span><span class="sxs-lookup"><span data-stu-id="51cd2-156">The role is indicated by the IsSender property in the node.</span></span> <span data-ttu-id="51cd2-157">对于不适用于发送方和接收方角色的节点（PartnerAgreement、PartnerBatchUpdatable、PartnerAS2Updatable 和 GlobalCommon），IsSender 始终为 False。</span><span class="sxs-lookup"><span data-stu-id="51cd2-157">For those nodes that are not used for both sender and receiver roles (PartnerAgreement, PartnerBatchUpdatable, PartnerAS2Updatable, and GlobalCommon), IsSender is always False.</span></span>  
  
 <span data-ttu-id="51cd2-158">无论 IsSender 设置为 True 还是 False，PartnerEdifact 和 PartnerX12 节点都包含接收方和发送方角色的属性。</span><span class="sxs-lookup"><span data-stu-id="51cd2-158">The PartnerEdifact and PartnerX12 nodes contain properties for both the receiver and sender roles, whether or not IsSender is set to True or False.</span></span> <span data-ttu-id="51cd2-159">例如，即使 IsSender 为 True，PartnerEdifact 仍将包含 Una1 字段（适用于作为交换接收方的参与方）。</span><span class="sxs-lookup"><span data-stu-id="51cd2-159">For example, PartnerEdifact will include a Una1 field (used for the party as an interchange receiver), even when IsSender is True.</span></span> <span data-ttu-id="51cd2-160">即使 IsSender 为 False，PartnerEdifact 仍将包含 Unb5CheckDup 字段（适用于作为交换发送方的参与方）。</span><span class="sxs-lookup"><span data-stu-id="51cd2-160">PartnerEdifact will also include a Unb5CheckDup field (used for the party as an interchange sender), even when IsSender is False.</span></span> <span data-ttu-id="51cd2-161">但是，如果 IsSender 为 True，作为交换接收方的参与方的字段则不会在 UI 中或者由引擎使用，而是对该字段赋予默认值。</span><span class="sxs-lookup"><span data-stu-id="51cd2-161">However, when IsSender is True, the fields for the party as an interchange receiver are not used in the UI or by the engine, but are given default values.</span></span> <span data-ttu-id="51cd2-162">同样，如果 IsSender 为 False，作为交换发送方的参与方的字段则不会在 UI 中或者由引擎使用，而是向该字段赋予默认值。</span><span class="sxs-lookup"><span data-stu-id="51cd2-162">Likewise, when IsSender is False, the fields for the party as an interchange sender are not used in the UI or by the engine, but are given default values.</span></span>  
  
 <span data-ttu-id="51cd2-163">如果属性的默认值为空，则不会将该字段包含在绑定文件中，除非向此字段赋予一个值。</span><span class="sxs-lookup"><span data-stu-id="51cd2-163">If the default of a property is null, the field will not be included in the binding file unless that field has been given a value.</span></span>  
  
 <span data-ttu-id="51cd2-164">绑定文件数据保存在 BizTalk 管理数据库 (BizTalkMgmtDb) 的表中。</span><span class="sxs-lookup"><span data-stu-id="51cd2-164">Binding file data is saved in tables of the BizTalk Management database (BizTalkMgmtDb).</span></span>