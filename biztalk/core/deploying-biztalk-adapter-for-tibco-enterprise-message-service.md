---
title: 用于 TIBCO EMS 将绑定导入 |Microsoft Docs
description: 部署用于 TIBCO Enterprise Message Service 应用程序在 BizTalk Server 中使用导入绑定功能在 BizTalk 适配器
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90d083833e7961770c6ecd535e9ed3e5143be30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981358"
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a><span data-ttu-id="79004-103">部署 TIBCO EMS 端口和程序集</span><span class="sxs-lookup"><span data-stu-id="79004-103">Deploy TIBCO EMS ports and assemblies</span></span>

## <a name="overview"></a><span data-ttu-id="79004-104">概述</span><span class="sxs-lookup"><span data-stu-id="79004-104">Overview</span></span>
<span data-ttu-id="79004-105">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="79004-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="79004-106"> 导出到 XML 文件发送端口/接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="79004-106"> exports send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="79004-107">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="79004-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
- <span data-ttu-id="79004-108">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其中删除。</span><span class="sxs-lookup"><span data-stu-id="79004-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
- <span data-ttu-id="79004-109">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载。</span><span class="sxs-lookup"><span data-stu-id="79004-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
- <span data-ttu-id="79004-110">将 BizTalk 程序集绑定信息导入到绑定文件或从中导出。</span><span class="sxs-lookup"><span data-stu-id="79004-110">Import or export BizTalk assembly binding information to and from binding files.</span></span>  
  
  <span data-ttu-id="79004-111">有关如何使用信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="79004-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79004-112">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上装有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="79004-112">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="79004-113">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="79004-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="79004-114">确认您的安装程序</span><span class="sxs-lookup"><span data-stu-id="79004-114">Confirm your setup</span></span>
<span data-ttu-id="79004-115">在使用 BizTalk Server 导入绑定文件之前，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="79004-115">Before you use BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="79004-116">用于响应的文件夹必须存在，并且在新计算机上必须相同；否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="79004-116">The folders for the responses must exist and be identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="79004-117">如果在配置中存在 TIBCO Enterprise Message Service 系统密码，则必须在绑定文件中另存为 \*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79004-117">TIBCO Enterprise Message Service system passwords, if present in the configuration, must be saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="79004-118">请参阅**限制**本主题中。</span><span class="sxs-lookup"><span data-stu-id="79004-118">See **Limitations** in this topic.</span></span>


## <a name="clean-the-target-computer"></a><span data-ttu-id="79004-119">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="79004-119">Clean the target computer</span></span>
<span data-ttu-id="79004-120">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="79004-120">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="79004-121">当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="79004-121">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  

<span data-ttu-id="79004-122">在导入之前，删除任何发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="79004-122">Before you import, remove any send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="79004-123">如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="79004-123">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

<span data-ttu-id="79004-124">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="79004-124">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a><span data-ttu-id="79004-125">限制</span><span class="sxs-lookup"><span data-stu-id="79004-125">Limitations</span></span>
<span data-ttu-id="79004-126">传输适配器密码存储为星号 (\*\*\*\*\*\*) 在绑定文件中的已导出的 BizTalk Server 中，并且传递至中相同的管理组件格式。</span><span class="sxs-lookup"><span data-stu-id="79004-126">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="79004-127">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="79004-127">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="79004-128">输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。</span><span class="sxs-lookup"><span data-stu-id="79004-128">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="79004-129">这是一项已知的缺限。</span><span class="sxs-lookup"><span data-stu-id="79004-129">This is a known limitation.</span></span> <span data-ttu-id="79004-130">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="79004-130">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="79004-131">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="79004-131">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="79004-132">下一次使用该文件导入绑定信息时，必须使用传输属性页用户界面输入密码。</span><span class="sxs-lookup"><span data-stu-id="79004-132">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="79004-133">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="79004-133">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="79004-134">在这种情况下，必须在成功完成导入操作后从绑定文件中删除密码。</span><span class="sxs-lookup"><span data-stu-id="79004-134">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
 
### <a name="password-limitation-workaround"></a><span data-ttu-id="79004-135">密码限制的解决方法</span><span class="sxs-lookup"><span data-stu-id="79004-135">Password Limitation Workaround</span></span>  
 <span data-ttu-id="79004-136">若要解决此密码限制问题，可使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="79004-136">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="79004-137">在导入之前编辑绑定文件，将星号替换为明文密码。</span><span class="sxs-lookup"><span data-stu-id="79004-137">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="79004-138">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="79004-138">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="79004-139">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="79004-139">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="79004-140">输入正确的密码使用**传输属性**导入绑定文件后在 BizTalk Server 管理控制台中的页。</span><span class="sxs-lookup"><span data-stu-id="79004-140">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79004-141">只有当目标计算机上安装了 Visual Studio 或者您开发了一个自定义工具时，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="79004-141">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="79004-142">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="79004-142">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="79004-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79004-143">Next steps</span></span>
[<span data-ttu-id="79004-144">在您的业务流程中使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="79004-144">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling5.md)