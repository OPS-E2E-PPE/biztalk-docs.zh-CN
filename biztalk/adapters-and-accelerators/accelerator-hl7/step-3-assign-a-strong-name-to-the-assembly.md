---
title: 步骤 3：对程序集分配强名称 |Microsoft Docs
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
ms.openlocfilehash: 01e98a471e2c91c463b7ead725cef61be1a52d92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288928"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="f0f58-102">步骤 3：对程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="f0f58-102">Step 3: Assign a Strong Name to the Assembly</span></span>
<span data-ttu-id="f0f58-103">在此步骤中，创建并分配强名称[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="f0f58-103">In this step, you create and assign a strong name for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] assembly.</span></span> <span data-ttu-id="f0f58-104">强名称的程序集提供多个安全优势和所需部署到全局程序集缓存 (GAC) 中的项目。</span><span class="sxs-lookup"><span data-stu-id="f0f58-104">A strong-named assembly provides several security benefits and is required in order to deploy your project in the global assembly cache (GAC).</span></span> <span data-ttu-id="f0f58-105">强名称通过分配的数字签名和唯一的密钥对保证唯一性的程序集。</span><span class="sxs-lookup"><span data-stu-id="f0f58-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="f0f58-106">这还可通过确保没有人可以生成的程序集的后续版本的程序集的沿袭。</span><span class="sxs-lookup"><span data-stu-id="f0f58-106">This also protects the lineage of the assembly by ensuring that no one can generate a subsequent version of the assembly.</span></span> <span data-ttu-id="f0f58-107">最后，强名称提供可靠的完整性检查以确保自您生成后，未更改的程序集的内容。</span><span class="sxs-lookup"><span data-stu-id="f0f58-107">Lastly, a strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since you built it.</span></span>  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="f0f58-108">若要对程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="f0f58-108">To assign a strong name to the assembly</span></span>  
  
1. <span data-ttu-id="f0f58-109">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-109">Start **Visual Studio Command Prompt**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f0f58-110">如果你已创建强名称密钥，则可以重用它。</span><span class="sxs-lookup"><span data-stu-id="f0f58-110">If you have already created a strong name key, you can reuse it.</span></span>  
  
2. <span data-ttu-id="f0f58-111">在命令提示符处，转到<strong>\<*驱动器*\>: \Tutorial\BTAHL7V22Common</strong> (其中\<*驱动器*\>是你安装的驱动器号），然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-111">At the command prompt, move to<strong>\<*drive*\>:\Tutorial\BTAHL7V22Common</strong> (where \<*drive*\> is your installation drive letter) and then press **Enter**.</span></span>  
  
3. <span data-ttu-id="f0f58-112">在命令提示符处，键入**sn – k key.snk**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-112">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="f0f58-113">出现一条消息，指示[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]密钥对写入密钥文件 key.snk。</span><span class="sxs-lookup"><span data-stu-id="f0f58-113">A message appears indicating that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] wrote the key pair to the key file key.snk.</span></span>  
  
4. <span data-ttu-id="f0f58-114">在解决方案资源管理器中右键单击**BTAHL7V22Common**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-114">In Solution Explorer, right-click the **BTAHL7V22Common** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="f0f58-115">在 BTAHL7V22Common 属性页对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-115">In the BTAHL7V22Common Property Pages dialog box, click **Assembly**.</span></span>  
  
6. <span data-ttu-id="f0f58-116">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="f0f58-116">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7. <span data-ttu-id="f0f58-117">在程序集密钥文件对话框中，浏览到 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common\key.snk**，单击**打开**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-117">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk**, click **Open**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="f0f58-118">在解决方案资源管理器中右键单击**BTAHL7V22Common**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="f0f58-118">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="f0f58-119">创建可以从下一个项目引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f0f58-119">creates an assembly that you can reference from your next project.</span></span>  
  
9. <span data-ttu-id="f0f58-120">BTAHL7V2XCommon 项目重复步骤 4 到 8。</span><span class="sxs-lookup"><span data-stu-id="f0f58-120">Repeat steps 4 through 8 for the BTAHL7V2XCommon project.</span></span>  
  
   <span data-ttu-id="f0f58-121">请继续执行[步骤 4:创建架构](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="f0f58-121">Proceed to [Step 4: Create the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f58-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f58-122">See Also</span></span>  
 [<span data-ttu-id="f0f58-123">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="f0f58-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)