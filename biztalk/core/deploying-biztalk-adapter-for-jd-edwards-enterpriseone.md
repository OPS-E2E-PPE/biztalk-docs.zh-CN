---
title: "导入博士 Edwards EnterpriseOne 应用程序 |Microsoft 文档"
description: "确认安装程序，导入应用程序绑定文件，并查看博士 Edwards EnterpriseOne 适配器在 BizTalk 的限制"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55374c87192c993e26cc11cb496d89074d527868
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="e890b-103">导入博士 Edwards EnterpriseOne 应用程序</span><span class="sxs-lookup"><span data-stu-id="e890b-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="e890b-104">概述</span><span class="sxs-lookup"><span data-stu-id="e890b-104">Overview</span></span>
<span data-ttu-id="e890b-105">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="e890b-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e890b-106">发送/接收端口的位置将配置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="e890b-106"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="e890b-107">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e890b-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="e890b-108">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其删除</span><span class="sxs-lookup"><span data-stu-id="e890b-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="e890b-109">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载</span><span class="sxs-lookup"><span data-stu-id="e890b-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="e890b-110">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其导出</span><span class="sxs-lookup"><span data-stu-id="e890b-110">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
<span data-ttu-id="e890b-111">若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署的端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e890b-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e890b-112">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e890b-112">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="e890b-113">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e890b-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="e890b-114">确认你的设置</span><span class="sxs-lookup"><span data-stu-id="e890b-114">Confirm your setup</span></span>
<span data-ttu-id="e890b-115">在使用 BizTalk Server 导入绑定文件之前，必须验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="e890b-115">Before you use the BizTalk Server to import a binding file, you must verify the following:</span></span>  
  
-   <span data-ttu-id="e890b-116">CLASSPATH 指向特定于 JD Edwards EnterpriseOne 文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="e890b-116">The CLASSPATH is pointing to a specific location for the JD Edwards EnterpriseOne-specific files.</span></span> <span data-ttu-id="e890b-117">验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e890b-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="e890b-118">用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e890b-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="e890b-119">如果在配置中存在 JD Edwards EnterpriseOne 系统密码，则在绑定文件中另存为 *****。</span><span class="sxs-lookup"><span data-stu-id="e890b-119">JD Edwards EnterpriseOne system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="e890b-120">有关详细信息，请参阅**限制**本主题中。</span><span class="sxs-lookup"><span data-stu-id="e890b-120">For more information, see **Limitations** in this topic.</span></span>

## <a name="clean-the-target-computer"></a><span data-ttu-id="e890b-121">清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="e890b-121">Clean the target computer</span></span>
<span data-ttu-id="e890b-122">当你重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置已替换为 XML 绑定文件中时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="e890b-122">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
<span data-ttu-id="e890b-123">在导入之前，删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="e890b-123">Before you import, remove Send ports and Receive locations bound to the orchestration.</span></span> <span data-ttu-id="e890b-124">如果未安装目标计算机上安装的 Visual Studio，你可以通过运行脚本中删除的端口：</span><span class="sxs-lookup"><span data-stu-id="e890b-124">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="e890b-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="e890b-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="e890b-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="e890b-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  

<span data-ttu-id="e890b-127">例如，从命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="e890b-127">For example, from a command prompt run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a><span data-ttu-id="e890b-128">限制</span><span class="sxs-lookup"><span data-stu-id="e890b-128">Limitations</span></span>
<span data-ttu-id="e890b-129">传输适配器密码为星号 （*） 存储在由导出绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将它传递给相同的格式中的管理组件。</span><span class="sxs-lookup"><span data-stu-id="e890b-129">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="e890b-130">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="e890b-130">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="e890b-131">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="e890b-131">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="e890b-132">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="e890b-132">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="e890b-133">下次使用文件导入绑定信息，你必须通过使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="e890b-133">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="e890b-134">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="e890b-134">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="e890b-135">在这种情况下，必须从绑定文件删除密码，导入操作成功完成后。</span><span class="sxs-lookup"><span data-stu-id="e890b-135">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="e890b-136">要解决的密码限制</span><span class="sxs-lookup"><span data-stu-id="e890b-136">Work around the password limitation</span></span>  
  
1.  <span data-ttu-id="e890b-137">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="e890b-137">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="e890b-138">使用的 SSO 选项需要在没有额外的工作;仅导入的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="e890b-138">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="e890b-139">验证逻辑的系统和传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="e890b-139">Verify the Logical system and the Transmit and Receive services.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="e890b-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e890b-140">Next steps</span></span>
[<span data-ttu-id="e890b-141">使用 BizTalk Server 中的异常处理您的业务流程</span><span class="sxs-lookup"><span data-stu-id="e890b-141">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling3.md)