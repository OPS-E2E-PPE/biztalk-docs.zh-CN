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
ms.openlocfilehash: b84730a5f88b36897114fb068b0d2ebbabf3f717
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352134"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="06088-103">JD Edwards EnterpriseOne 应用程序导入</span><span class="sxs-lookup"><span data-stu-id="06088-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="06088-104">概述</span><span class="sxs-lookup"><span data-stu-id="06088-104">Overview</span></span>
<span data-ttu-id="06088-105">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以复制端口和目标计算机上的程序集。</span><span class="sxs-lookup"><span data-stu-id="06088-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="06088-106">BizTalk Server 发送端口/接收位置将配置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="06088-106">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="06088-107">BizTalk Server 可用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="06088-107">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="06088-108">部署或 BizTalk 配置数据库中删除 BizTalk Server 程序集</span><span class="sxs-lookup"><span data-stu-id="06088-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="06088-109">安装或卸载的全局程序集缓存 (GAC) 中的程序集</span><span class="sxs-lookup"><span data-stu-id="06088-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="06088-110">导入或导出 BizTalk Server 程序集绑定信息与绑定文件</span><span class="sxs-lookup"><span data-stu-id="06088-110">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  

<span data-ttu-id="06088-111">若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]若要部署端口和程序集，请参阅[如何导出 BizTalk 应用程序的绑定](../core/how-to-export-bindings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="06088-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06088-112">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器只要求在源 （开发） 计算机上具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="06088-112">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="06088-113">Visual Studio 不需要在生产计算机上。</span><span class="sxs-lookup"><span data-stu-id="06088-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="06088-114">确认您的安装程序</span><span class="sxs-lookup"><span data-stu-id="06088-114">Confirm your setup</span></span>
<span data-ttu-id="06088-115">使用 BizTalk Server 导入绑定文件之前，请验证以下：</span><span class="sxs-lookup"><span data-stu-id="06088-115">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="06088-116">CLASSPATH 指向 JD Edwards 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="06088-116">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="06088-117">验证这些文件的位置是相同的新计算机上，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="06088-118">用于响应文件夹存在并在新计算机上完全相同或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="06088-119">JD Edwards 系统密码，如果存在在配置中，将保存为 \* \* \* 绑定文件中。</span><span class="sxs-lookup"><span data-stu-id="06088-119">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="06088-120">请参阅**限制**本主题中。</span><span class="sxs-lookup"><span data-stu-id="06088-120">See **Limitations** in this topic.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="06088-121">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="06088-121">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="06088-122">在目标计算机上部署绑定文件 （和程序集），发送端口和接收位置将替换 XML 绑定文件中导入它们。</span><span class="sxs-lookup"><span data-stu-id="06088-122">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="06088-123">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="06088-123">Clean the target computer</span></span>
<span data-ttu-id="06088-124">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="06088-124">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="06088-125">当将绑定文件 （和程序集） 部署的目标计算机上，发送端口和接收位置将替换 XML 绑定文件中所导入。</span><span class="sxs-lookup"><span data-stu-id="06088-125">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="06088-126">在导入之前，删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="06088-126">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="06088-127">如果没有在目标计算机上安装 Microsoft Visual Studio，则可以通过运行这些脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="06088-127">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="06088-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="06088-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="06088-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="06088-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="06088-130">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="06088-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a><span data-ttu-id="06088-131">限制</span><span class="sxs-lookup"><span data-stu-id="06088-131">Limitations</span></span>
<span data-ttu-id="06088-132">传输适配器密码存储为星号 (\*\*\*\*\*\*) 中的绑定文件导出的 BizTalk 部署向导，并传递到管理相同的格式中的组件。</span><span class="sxs-lookup"><span data-stu-id="06088-132">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="06088-133">将星号替换随机字母数字值 （即，不正确的密码） 导入之前编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-133">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="06088-134">然后输入正确的密码使用**传输属性**导入绑定文件后的页。</span><span class="sxs-lookup"><span data-stu-id="06088-134">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="06088-135">在导出绑定信息时，得到的绑定文件不包含任何传输所使用的密码中的适配器接收位置/发送端口。</span><span class="sxs-lookup"><span data-stu-id="06088-135">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="06088-136">这可以防止以明文形式显示密码信息。</span><span class="sxs-lookup"><span data-stu-id="06088-136">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="06088-137">下次使用该文件导入绑定信息时，你必须使用传输属性页用户界面中输入的密码。</span><span class="sxs-lookup"><span data-stu-id="06088-137">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="06088-138">或者，暂时可以通过将密码输入到其导入前修改绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-138">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="06088-139">在这种情况下，你必须删除密码从绑定文件导入操作已成功完成后。</span><span class="sxs-lookup"><span data-stu-id="06088-139">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06088-140">导入到某一.msi 文件时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含针对任何企业适配器的绑定信息的应用程序可能会收到导入错误消息。</span><span class="sxs-lookup"><span data-stu-id="06088-140">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="06088-141">支持的修补程序是 Microsoft 提供的以及在错误的完整说明[ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us)。</span><span class="sxs-lookup"><span data-stu-id="06088-141">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="06088-142">解决此密码限制</span><span class="sxs-lookup"><span data-stu-id="06088-142">Work around the password limitation</span></span>  

<span data-ttu-id="06088-143">**选项 1**</span><span class="sxs-lookup"><span data-stu-id="06088-143">**Option 1**</span></span>  

- <span data-ttu-id="06088-144">在导入之前，请通过将星号替换纯文本更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-144">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="06088-145">出于安全原因，这不被建议。</span><span class="sxs-lookup"><span data-stu-id="06088-145">This is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="06088-146">在导入之前，通过将星号替换某些无效的值 （即，不正确的密码） 来更新绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-146">Before you import, update the binding file by replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="06088-147">导入后，请输入正确的密码使用**传输属性**。</span><span class="sxs-lookup"><span data-stu-id="06088-147">After you import, enter the correct password using the **Transport Properties**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="06088-148">这种解决可仅当目标计算机上或通过开发一个自定义工具来安装 Microsoft Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="06088-148">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
<span data-ttu-id="06088-149">**选项 2**</span><span class="sxs-lookup"><span data-stu-id="06088-149">**Option 2**</span></span>  
  
1.  <span data-ttu-id="06088-150">使用企业单一登录，而不是使用密码。</span><span class="sxs-lookup"><span data-stu-id="06088-150">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="06088-151">使用 SSO 选项需要任何额外操作;仅导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="06088-151">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="06088-152">验证逻辑系统以及传输和接收服务。</span><span class="sxs-lookup"><span data-stu-id="06088-152">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="06088-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="06088-153">Next steps</span></span>
[<span data-ttu-id="06088-154">在您的业务流程中使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="06088-154">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling1.md)