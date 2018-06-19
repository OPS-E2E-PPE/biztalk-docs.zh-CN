---
title: 导入 PeopleSoft 应用程序 |Microsoft 文档
description: 使用 XML 绑定文件来将 PeopleSoft 适配器应用程序导入到 BizTalk Server 中，并且当导入时读取的任何限制
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f53d1b4-e1df-41ff-b554-1bb1d20b9111
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed076bd238eff5106bb0b2f08449144d922fed4d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970819"
---
# <a name="deploy-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="e4353-103">为 PeopleSoft 企业部署的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="e4353-103">Deploy BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="e4353-104">本部分提供有关部署 PeopleSoft Enterprise 的 BizTalk 适配器的信息。</span><span class="sxs-lookup"><span data-stu-id="e4353-104">This section provides information about deploying BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

## <a name="overview"></a><span data-ttu-id="e4353-105">概述</span><span class="sxs-lookup"><span data-stu-id="e4353-105">Overview</span></span>
<span data-ttu-id="e4353-106">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="e4353-106">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e4353-107"> 发送/接收端口的位置将配置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e4353-107"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="e4353-108">您可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="e4353-108">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
-   <span data-ttu-id="e4353-109">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。</span><span class="sxs-lookup"><span data-stu-id="e4353-109">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="e4353-110">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。</span><span class="sxs-lookup"><span data-stu-id="e4353-110">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="e4353-111">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其中导出。</span><span class="sxs-lookup"><span data-stu-id="e4353-111">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
<span data-ttu-id="e4353-112">若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4353-112">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4353-113">Microsoft BizTalk Adapter for PeopleSoft 企业仅需要源 （开发） 计算机上安装 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e4353-113">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="e4353-114">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e4353-114">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="e4353-115">确认你的设置</span><span class="sxs-lookup"><span data-stu-id="e4353-115">Confirm your setup</span></span>
<span data-ttu-id="e4353-116">在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入绑定文件之前，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="e4353-116">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="e4353-117">CLASSPATH 指向 PeopleSoft 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="e4353-117">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="e4353-118">验证这些文件的位置是否在新计算机上相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e4353-118">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="e4353-119">响应的文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e4353-119">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="e4353-120">如果在配置中存在 PeopleSoft Enterprise 系统密码，则在绑定文件中另存为 \*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e4353-120">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="e4353-121">请参阅**限制**本主题中。</span><span class="sxs-lookup"><span data-stu-id="e4353-121">See **Limitations** in this topic.</span></span>

> [!NOTE]
>  <span data-ttu-id="e4353-122">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="e4353-122">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="e4353-123">如果在目标计算机上部署绑定文件和程序集，则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="e4353-123">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="e4353-124">有关导入绑定文件的分步指导，请参阅[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="e4353-124">For step-by-step directions about importing binding files, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span> 
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="e4353-125">清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="e4353-125">Clean the target computer</span></span>
<span data-ttu-id="e4353-126">若要清除目标计算机上部署新的应用程序、 删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4353-126">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="e4353-127">如果没有在目标计算机上安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，则可通过运行下面的脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="e4353-127">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="e4353-128">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="e4353-128">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="e4353-129">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="e4353-129">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="e4353-130">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="e4353-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a><span data-ttu-id="e4353-131">限制</span><span class="sxs-lookup"><span data-stu-id="e4353-131">Limitations</span></span>
<span data-ttu-id="e4353-132">传输适配器密码为星号 （\*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。</span><span class="sxs-lookup"><span data-stu-id="e4353-132">The Transport Adapter password is stored as asterisks (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="e4353-133">當您匯出繫結資訊時，所產生的繫結檔案不會包含傳輸配接器在接收位置/傳送埠中使用的任何密碼。</span><span class="sxs-lookup"><span data-stu-id="e4353-133">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="e4353-134">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="e4353-134">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="e4353-135">下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。</span><span class="sxs-lookup"><span data-stu-id="e4353-135">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="e4353-136">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="e4353-136">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="e4353-137">在这种情况下，必须在完成导入操作后从绑定文件中删除密码。</span><span class="sxs-lookup"><span data-stu-id="e4353-137">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

### <a name="work-around-the-password-limitation"></a><span data-ttu-id="e4353-138">要解决的密码限制</span><span class="sxs-lookup"><span data-stu-id="e4353-138">Work around the password limitation</span></span>  

<span data-ttu-id="e4353-139">**选项 1**</span><span class="sxs-lookup"><span data-stu-id="e4353-139">**Option 1**</span></span>   
  
-   <span data-ttu-id="e4353-140">在导入之前，请通过将替换为纯文本的星号更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e4353-140">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e4353-141">出于安全考虑，不建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e4353-141">This practice is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="e4353-142">在导入之前，更新绑定 fileby 星号替换某个垃圾值 （即，不正确的密码）。</span><span class="sxs-lookup"><span data-stu-id="e4353-142">Before you import, update the binding fileby replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="e4353-143">导入后，输入中的正确密码**传输属性**BizTalk Server 管理中。</span><span class="sxs-lookup"><span data-stu-id="e4353-143">After you import, enter the correct password in the **Transport Properties** in BizTalk Server Administration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e4353-144">只有当目标计算机上安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 或者您开发了一个自定义工具时，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="e4353-144">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
<span data-ttu-id="e4353-145">**选项 2**</span><span class="sxs-lookup"><span data-stu-id="e4353-145">**Option 2**</span></span>  
  
-   <span data-ttu-id="e4353-146">使用企业单一登录 (SSO) 而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="e4353-146">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span> <span data-ttu-id="e4353-147">使用 SSO 选项时需要导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e4353-147">Using the SSO option requires an import of the binding file.</span></span>  
  
- <span data-ttu-id="e4353-148">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="e4353-148">Verify the logical system and the Transmit and Receive services.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="e4353-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e4353-149">Next steps</span></span>
[<span data-ttu-id="e4353-150">使用 BizTalk Server 中的异常处理您的业务流程</span><span class="sxs-lookup"><span data-stu-id="e4353-150">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling2.md)