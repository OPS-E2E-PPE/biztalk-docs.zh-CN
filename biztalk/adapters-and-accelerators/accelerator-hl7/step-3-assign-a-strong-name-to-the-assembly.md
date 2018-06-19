---
title: 步骤 3： 向程序集分配强名称 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57368dbbb2d8ecaa6621707ea7b989bf7f5b005d
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "26004950"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="a00ba-102">步骤 3： 向程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="a00ba-102">Step 3: Assign a Strong Name to the Assembly</span></span>
<span data-ttu-id="a00ba-103">在此步骤中，创建并分配强名称的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="a00ba-103">In this step, you create and assign a strong name for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] assembly.</span></span> <span data-ttu-id="a00ba-104">具有强名称程序集提供多个安全优势，并要将部署到全局程序集缓存 (GAC) 中的项目需要。</span><span class="sxs-lookup"><span data-stu-id="a00ba-104">A strong-named assembly provides several security benefits and is required in order to deploy your project in the global assembly cache (GAC).</span></span> <span data-ttu-id="a00ba-105">强名称保证通过将数字签名和唯一的密钥对分配的程序集的唯一性。</span><span class="sxs-lookup"><span data-stu-id="a00ba-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="a00ba-106">这还可通过确保没有人可以生成程序集的后续版本的程序集的沿袭。</span><span class="sxs-lookup"><span data-stu-id="a00ba-106">This also protects the lineage of the assembly by ensuring that no one can generate a subsequent version of the assembly.</span></span> <span data-ttu-id="a00ba-107">最后，强名称提供可靠的完整性检查，若要确保以来生成，未更改的程序集的内容。</span><span class="sxs-lookup"><span data-stu-id="a00ba-107">Lastly, a strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since you built it.</span></span>  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="a00ba-108">若要向程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="a00ba-108">To assign a strong name to the assembly</span></span>  
  
1.  <span data-ttu-id="a00ba-109">启动 **Visual Studio 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-109">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a00ba-110">如果你已创建强名称密钥，则可以重用它。</span><span class="sxs-lookup"><span data-stu-id="a00ba-110">If you have already created a strong name key, you can reuse it.</span></span>  
  
2.  <span data-ttu-id="a00ba-111">在命令提示符下，将移到**\<*驱动器*\>: \Tutorial\BTAHL7V22Common** (其中\<*驱动器*\>是你安装的驱动器号），然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-111">At the command prompt, move to**\<*drive*\>:\Tutorial\BTAHL7V22Common** (where \<*drive*\> is your installation drive letter) and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="a00ba-112">在命令提示符处，键入**sn-k key.snk**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-112">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="a00ba-113">显示一条消息，指示[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]已的密钥对写入到密钥文件命名为 key.snk。</span><span class="sxs-lookup"><span data-stu-id="a00ba-113">A message appears indicating that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] wrote the key pair to the key file key.snk.</span></span>  
  
4.  <span data-ttu-id="a00ba-114">在解决方案资源管理器，右键单击**BTAHL7V22Common**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-114">In Solution Explorer, right-click the **BTAHL7V22Common** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a00ba-115">在 BTAHL7V22Common 属性页对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-115">In the BTAHL7V22Common Property Pages dialog box, click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="a00ba-116">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="a00ba-116">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7.  <span data-ttu-id="a00ba-117">在程序集密钥文件对话框中，浏览到 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\key.snk**，单击**打开**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-117">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk**, click **Open**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a00ba-118">在解决方案资源管理器，右键单击**BTAHL7V22Common**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="a00ba-118">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a00ba-119">创建可以从下一个项目引用程序集。</span><span class="sxs-lookup"><span data-stu-id="a00ba-119"> creates an assembly that you can reference from your next project.</span></span>  
  
9. <span data-ttu-id="a00ba-120">对 BTAHL7V2XCommon 项目重复步骤 4 至 8。</span><span class="sxs-lookup"><span data-stu-id="a00ba-120">Repeat steps 4 through 8 for the BTAHL7V2XCommon project.</span></span>  
  
 <span data-ttu-id="a00ba-121">继续执行[步骤 4： 创建架构](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="a00ba-121">Proceed to [Step 4: Create the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00ba-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a00ba-122">See Also</span></span>  
 [<span data-ttu-id="a00ba-123">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="a00ba-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)