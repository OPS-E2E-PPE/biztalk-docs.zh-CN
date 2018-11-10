---
title: 导入 JD Edwards EnterpriseOne 应用程序 |Microsoft Docs
description: 确认设置，导入应用程序绑定文件，并查看 JD Edwards EnterpriseOne 适配器在 BizTalk 中的限制
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c6f24ff4cb7060d0cddf29d82f4035d8407dca
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753189"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="4c7f1-103">JD Edwards EnterpriseOne 应用程序导入</span><span class="sxs-lookup"><span data-stu-id="4c7f1-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="4c7f1-104">概述</span><span class="sxs-lookup"><span data-stu-id="4c7f1-104">Overview</span></span>
<span data-ttu-id="4c7f1-105">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4c7f1-106">导出的发送端口/接收位置配置为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-106">exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="4c7f1-107">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4c7f1-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
- <span data-ttu-id="4c7f1-108">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集部署到 BizTalk 配置数据库中或从其删除</span><span class="sxs-lookup"><span data-stu-id="4c7f1-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
- <span data-ttu-id="4c7f1-109">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载</span><span class="sxs-lookup"><span data-stu-id="4c7f1-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
- <span data-ttu-id="4c7f1-110">将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 程序集绑定信息导入到绑定文件或从其导出</span><span class="sxs-lookup"><span data-stu-id="4c7f1-110">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
<span data-ttu-id="4c7f1-111">若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c7f1-112">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-112">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="4c7f1-113">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="4c7f1-114">确认您的安装程序</span><span class="sxs-lookup"><span data-stu-id="4c7f1-114">Confirm your setup</span></span>
<span data-ttu-id="4c7f1-115">在使用 BizTalk Server 导入绑定文件之前，必须验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="4c7f1-115">Before you use the BizTalk Server to import a binding file, you must verify the following:</span></span>  
  
-   <span data-ttu-id="4c7f1-116">CLASSPATH 指向特定于 JD Edwards EnterpriseOne 文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-116">The CLASSPATH is pointing to a specific location for the JD Edwards EnterpriseOne-specific files.</span></span> <span data-ttu-id="4c7f1-117">验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="4c7f1-118">用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="4c7f1-119">JD Edwards EnterpriseOne 系统密码，如果存在在配置中，将另存为\* \* \* \* \*绑定文件中。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-119">JD Edwards EnterpriseOne system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="4c7f1-120">有关详细信息，请参阅**限制**本主题中。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-120">For more information, see **Limitations** in this topic.</span></span>

## <a name="clean-the-target-computer"></a><span data-ttu-id="4c7f1-121">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="4c7f1-121">Clean the target computer</span></span>
<span data-ttu-id="4c7f1-122">当重新绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换中的 XML 绑定文件时它们重新导入。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-122">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
<span data-ttu-id="4c7f1-123">在导入之前，删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-123">Before you import, remove Send ports and Receive locations bound to the orchestration.</span></span> <span data-ttu-id="4c7f1-124">如果未安装目标计算机上安装的 Visual Studio，则可以通过运行脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="4c7f1-124">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="4c7f1-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="4c7f1-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="4c7f1-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="4c7f1-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  

<span data-ttu-id="4c7f1-127">例如，从命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="4c7f1-127">For example, from a command prompt run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a><span data-ttu-id="4c7f1-128">限制</span><span class="sxs-lookup"><span data-stu-id="4c7f1-128">Limitations</span></span>
<span data-ttu-id="4c7f1-129">传输适配器密码存储为星级 (\*\*\*\*\*\*) 中导出的绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将其传递到中的管理组件相同的格式。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-129">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="4c7f1-130">在导入之前编辑绑定文件，将星号替换为某些无效的值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-130">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="4c7f1-131">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-131">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="4c7f1-132">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-132">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="4c7f1-133">下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-133">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="4c7f1-134">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-134">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="4c7f1-135">在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-135">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="4c7f1-136">解决此密码限制</span><span class="sxs-lookup"><span data-stu-id="4c7f1-136">Work around the password limitation</span></span>  
  
1.  <span data-ttu-id="4c7f1-137">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-137">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="4c7f1-138">使用 SSO 选项需要任何额外操作;仅导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-138">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="4c7f1-139">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="4c7f1-139">Verify the Logical system and the Transmit and Receive services.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="4c7f1-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4c7f1-140">Next steps</span></span>
[<span data-ttu-id="4c7f1-141">在您的业务流程中使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="4c7f1-141">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling3.md)