---
title: 用于 JD Edwards OneWorld 导入 BizTalk 适配器 |Microsoft Docs
description: 导入应用程序绑定文件，并查看 JD Edwards OneWorld 适配器在 BizTalk 中的任何限制。
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca65c71e14d488b264d861616fe170220ac249b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999214"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="75d25-103">JD Edwards EnterpriseOne 应用程序导入</span><span class="sxs-lookup"><span data-stu-id="75d25-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="75d25-104">概述</span><span class="sxs-lookup"><span data-stu-id="75d25-104">Overview</span></span>
<span data-ttu-id="75d25-105">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可在目标计算机上复制端口和程序集。</span><span class="sxs-lookup"><span data-stu-id="75d25-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="75d25-106">BizTalk Server 将发送端口/接收位置配置导出到一个 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="75d25-106">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="75d25-107">BizTalk Server 可用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="75d25-107">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="75d25-108">将 BizTalk Server 程序集部署到 BizTalk 配置数据库或从其删除</span><span class="sxs-lookup"><span data-stu-id="75d25-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="75d25-109">将程序集安装在全局程序集缓存 (GAC) 中或从其卸载</span><span class="sxs-lookup"><span data-stu-id="75d25-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="75d25-110">将 BizTalk Server 程序集绑定信息导入到绑定文件或从其导出</span><span class="sxs-lookup"><span data-stu-id="75d25-110">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  

<span data-ttu-id="75d25-111">若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="75d25-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75d25-112">JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源（开发）计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="75d25-112">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="75d25-113">在生产计算机上不要求使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="75d25-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="75d25-114">确认您的安装程序</span><span class="sxs-lookup"><span data-stu-id="75d25-114">Confirm your setup</span></span>
<span data-ttu-id="75d25-115">使用 BizTalk Server 导入绑定文件之前，请验证以下：</span><span class="sxs-lookup"><span data-stu-id="75d25-115">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="75d25-116">CLASSPATH 指向 JD Edwards 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="75d25-116">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="75d25-117">验证在新计算机上这些文件的位置是否相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75d25-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="75d25-118">用于响应的文件夹存在，并且在新计算机上相同，否则编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75d25-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="75d25-119">如果在配置中存在 JD Edwards 系统密码，则在绑定文件中另存为 \*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75d25-119">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="75d25-120">请参阅**限制**本主题中。</span><span class="sxs-lookup"><span data-stu-id="75d25-120">See **Limitations** in this topic.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="75d25-121">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="75d25-121">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="75d25-122">如果在目标计算机上部署绑定文件（和程序集），则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="75d25-122">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="75d25-123">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="75d25-123">Clean the target computer</span></span>
<span data-ttu-id="75d25-124">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="75d25-124">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="75d25-125">当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="75d25-125">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="75d25-126">在导入之前，删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="75d25-126">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="75d25-127">如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="75d25-127">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="75d25-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="75d25-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="75d25-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="75d25-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="75d25-130">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="75d25-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a><span data-ttu-id="75d25-131">限制</span><span class="sxs-lookup"><span data-stu-id="75d25-131">Limitations</span></span>
<span data-ttu-id="75d25-132">传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。</span><span class="sxs-lookup"><span data-stu-id="75d25-132">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="75d25-133">在导入之前编辑绑定文件，将星号替换为随机的字母数字值（即，不替换为正确密码）。</span><span class="sxs-lookup"><span data-stu-id="75d25-133">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="75d25-134">然后输入正确的密码使用**传输属性**导入绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="75d25-134">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="75d25-135">在导出绑定信息时，得到的绑定文件不包含传输适配器曾经在接收位置/发送端口中使用过的任何密码。</span><span class="sxs-lookup"><span data-stu-id="75d25-135">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="75d25-136">这样可防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="75d25-136">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="75d25-137">下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="75d25-137">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="75d25-138">或者，可以在导入前临时修改绑定文件，将密码输入到文件中。</span><span class="sxs-lookup"><span data-stu-id="75d25-138">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="75d25-139">在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。</span><span class="sxs-lookup"><span data-stu-id="75d25-139">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75d25-140">将 .msi 文件导入包含任何企业适配器的绑定信息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时，您可能会收到一条导入错误消息。</span><span class="sxs-lookup"><span data-stu-id="75d25-140">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="75d25-141">支持的修补程序是 Microsoft 提供的以及在错误的完整说明[ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us)。</span><span class="sxs-lookup"><span data-stu-id="75d25-141">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="75d25-142">解决此密码限制</span><span class="sxs-lookup"><span data-stu-id="75d25-142">Work around the password limitation</span></span>  

<span data-ttu-id="75d25-143">**选项 1**</span><span class="sxs-lookup"><span data-stu-id="75d25-143">**Option 1**</span></span>  

- <span data-ttu-id="75d25-144">在导入之前，请通过将星号替换纯文本更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75d25-144">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="75d25-145">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="75d25-145">This is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="75d25-146">在导入之前，通过将星号替换某些无效的值 （即，不正确的密码） 来更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75d25-146">Before you import, update the binding file by replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="75d25-147">导入后，请输入正确的密码使用**传输属性**。</span><span class="sxs-lookup"><span data-stu-id="75d25-147">After you import, enter the correct password using the **Transport Properties**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75d25-148">只有当目标计算机上安装了 Microsoft Visual Studio 或者开发一个自定义工具，才能使用这种解决方法。</span><span class="sxs-lookup"><span data-stu-id="75d25-148">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
<span data-ttu-id="75d25-149">**选项 2**</span><span class="sxs-lookup"><span data-stu-id="75d25-149">**Option 2**</span></span>  
  
1.  <span data-ttu-id="75d25-150">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="75d25-150">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="75d25-151">使用 SSO 选项需要任何额外操作;仅导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="75d25-151">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="75d25-152">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="75d25-152">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="75d25-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="75d25-153">Next steps</span></span>
[<span data-ttu-id="75d25-154">在您的业务流程中使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="75d25-154">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling1.md)