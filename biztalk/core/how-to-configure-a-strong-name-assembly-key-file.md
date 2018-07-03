---
title: 如何配置强名称程序集密钥文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5778a8ec-f5f7-4ae1-a57e-99f6503f044c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c98ad06e902d06f2d24ac5f6fb01a2228753795
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006790"
---
# <a name="how-to-configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="0bf87-102">如何配置强名称程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="0bf87-102">How to Configure a Strong Name Assembly Key File</span></span>
<span data-ttu-id="0bf87-103">在过程中部署 BizTalk 解决方案，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]首先生成程序集。</span><span class="sxs-lookup"><span data-stu-id="0bf87-103">In the process of deploying a BizTalk solution, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] first builds the assemblies.</span></span> <span data-ttu-id="0bf87-104">部署过程要求每个程序集都是强签名的。</span><span class="sxs-lookup"><span data-stu-id="0bf87-104">The deployment process requires that each assembly is strongly signed.</span></span> <span data-ttu-id="0bf87-105">强可以通过将项目与一个强名称程序集密钥文件相关联来签名你的程序集。</span><span class="sxs-lookup"><span data-stu-id="0bf87-105">You can strongly sign your assemblies by associating the project with a strong name assembly key file.</span></span> <span data-ttu-id="0bf87-106">如果你尚未这样做，则在从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署某一解决方案之前，使用以下过程生成一个强名称程序集密钥文件并将它分配给解决方案中的每个项目。</span><span class="sxs-lookup"><span data-stu-id="0bf87-106">If you haven't already done so, before deploying a solution from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], use the following procedure to generate a strong name assembly key file and assign it to each project in the solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0bf87-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="0bf87-107">Prerequisites</span></span>  
 <span data-ttu-id="0bf87-108">若要执行本主题中的过程，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="0bf87-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrator's group.</span></span> <span data-ttu-id="0bf87-109">此外，你的帐户还必须对全局程序集缓存 (GAC) 具有写权限。</span><span class="sxs-lookup"><span data-stu-id="0bf87-109">In addition, your account must have Write permissions on the global assembly cache (GAC).</span></span> <span data-ttu-id="0bf87-110">本地计算机的管理员帐户拥有此权限。</span><span class="sxs-lookup"><span data-stu-id="0bf87-110">The Administrators account on the local computer has this permission.</span></span>  
  
### <a name="to-configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="0bf87-111">配置强名称程序集密钥文件</span><span class="sxs-lookup"><span data-stu-id="0bf87-111">To configure a strong name assembly key file</span></span>  
  
1. <span data-ttu-id="0bf87-112">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="0bf87-112">Start **Visual Studio Command Prompt**.</span></span>  
  
2. <span data-ttu-id="0bf87-113">在命令提示符下，从你要存储密钥文件的文件夹，键入以下命令，然后按 Enter 键：</span><span class="sxs-lookup"><span data-stu-id="0bf87-113">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="0bf87-114">**sn /k***file_name* **.snk** </span><span class="sxs-lookup"><span data-stu-id="0bf87-114">**sn /k**  *file_name* **.snk**</span></span>  
  
    <span data-ttu-id="0bf87-115">示例： **sn /k ErrorHandling.snk**</span><span class="sxs-lookup"><span data-stu-id="0bf87-115">Example: **sn /k ErrorHandling.snk**</span></span>  
  
    <span data-ttu-id="0bf87-116">一条确认消息，**密钥对写入** \< *file_name*\>**.snk** `,`显示命令行上。</span><span class="sxs-lookup"><span data-stu-id="0bf87-116">A confirmation message, **Key pair written to** \<*file_name*\>**.snk**`,` displays on the command line.</span></span>  
  
3. <span data-ttu-id="0bf87-117">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0bf87-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Solution Explorer, right-click the project and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="0bf87-118">单击**签名**选项卡，选择**浏览**中**选择强名称密钥文件**下拉框。</span><span class="sxs-lookup"><span data-stu-id="0bf87-118">Click the **Signing** tab and choose **Browse** in the **Choose a strong name key file** drop down box.</span></span>  
  
5. <span data-ttu-id="0bf87-119">浏览到密钥文件，然后单击该文件。</span><span class="sxs-lookup"><span data-stu-id="0bf87-119">Browse to the key file and click it.</span></span> <span data-ttu-id="0bf87-120">单击**打开**，然后关闭项目属性。</span><span class="sxs-lookup"><span data-stu-id="0bf87-120">Click **Open**, and then close the project properties.</span></span>  
  
6. <span data-ttu-id="0bf87-121">对解决方案中你要使用此强名称程序集密钥文件部署的每个项目，都重复步骤 3 到 6。</span><span class="sxs-lookup"><span data-stu-id="0bf87-121">Repeat steps 3 through 6 for each project in the solution that you want to deploy using this strong name assembly key file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf87-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bf87-122">See Also</span></span>  
 [<span data-ttu-id="0bf87-123">将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="0bf87-123">Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application</span></span>](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)