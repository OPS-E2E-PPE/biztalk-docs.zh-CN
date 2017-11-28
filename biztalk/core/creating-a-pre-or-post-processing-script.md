---
title: "创建预或操作的后续处理脚本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts, post-processing
- scripts, pre-processing
- scripts, warnings
- scripts, applications
- applications, scripts
- scripts, deploying
- deploying, scripts
ms.assetid: d5fbaec8-fbfe-4ceb-8ba8-0933baa37a1f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532c730d5a654512610a37c9dac783fbc6a76d6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-pre--or-post-processing-script"></a><span data-ttu-id="81e47-102">创建预处理或后处理脚本</span><span class="sxs-lookup"><span data-stu-id="81e47-102">Creating a Pre- or Post-processing Script</span></span>
<span data-ttu-id="81e47-103">您可以在布署应用程序时创建脚本来执行操作，然后定义在部署过程中何时运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="81e47-103">You can create a script to perform actions when an application is deployed, and then define when it will run during the deployment process.</span></span> <span data-ttu-id="81e47-104">同一脚本中可以同时包含安装和清理代码，之间用环境变量分隔。</span><span class="sxs-lookup"><span data-stu-id="81e47-104">You can include both installation and cleanup code in the same script, using environment variables to delimit the code.</span></span> <span data-ttu-id="81e47-105">也可以向脚本中传递命令行参数。</span><span class="sxs-lookup"><span data-stu-id="81e47-105">You can also pass command-line arguments into the script.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="81e47-106">您始终应以无提示模式编写用于生产系统的脚本。</span><span class="sxs-lookup"><span data-stu-id="81e47-106">You should always write scripts intended for production systems in silent mode.</span></span> <span data-ttu-id="81e47-107">这是因为等待用户输入的脚本会导致 BizTalk 数据库锁定和无法访问，直到收到输入时为止。</span><span class="sxs-lookup"><span data-stu-id="81e47-107">This is because a script waiting for user input will cause the BizTalk databases to become locked and inaccessible until the input is received.</span></span>  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a><span data-ttu-id="81e47-108">指定脚本在部署期间何时运行</span><span class="sxs-lookup"><span data-stu-id="81e47-108">Specifying when a script will run during deployment</span></span>  
 <span data-ttu-id="81e47-109">通过将脚本作为 System.BizTalk:PreProcessingScript（预处理脚本）或 System.BizTalk:PostProcessingScript（后处理脚本）添加到应用程序，可以指定何时运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="81e47-109">You specify when a script will run when you add the script to an application by adding it as either a System.BizTalk:PreProcessingScript (pre-processing script) or a System.BizTalk:PostProcessingScript (post-processing script).</span></span>  
  
 <span data-ttu-id="81e47-110">预处理脚本和后处理脚本以如下方式运行：</span><span class="sxs-lookup"><span data-stu-id="81e47-110">Pre- and post-processing scripts run as follows:</span></span>  
  
-   <span data-ttu-id="81e47-111">预处理脚本在导入或安装过程开始时运行。</span><span class="sxs-lookup"><span data-stu-id="81e47-111">Pre-processing scripts run at the beginning of the import or installation process.</span></span>  
  
-   <span data-ttu-id="81e47-112">后处理脚本在导入或安装过程结束时运行。</span><span class="sxs-lookup"><span data-stu-id="81e47-112">Post-processing scripts run at the end of the import or installation process.</span></span>  
  
-   <span data-ttu-id="81e47-113">在卸载过程中，所有脚本的运行顺序与安装过程中的运行顺序相反。</span><span class="sxs-lookup"><span data-stu-id="81e47-113">During uninstallation, all scripts run in the opposite order that they run during installation.</span></span> <span data-ttu-id="81e47-114">因此，后处理脚本在卸载开始时运行，预处理脚本在卸载结束时运行。</span><span class="sxs-lookup"><span data-stu-id="81e47-114">Therefore, post-processing scripts run at the beginning of uninstallation and pre-processing scripts at the end of uninstallation.</span></span>  
  
-   <span data-ttu-id="81e47-115">如果安装失败，则会使用相应的回滚操作以相反顺序调用脚本。</span><span class="sxs-lookup"><span data-stu-id="81e47-115">If an installation fails, scripts are called in reverse order with the appropriate rollback action.</span></span>  
  
 <span data-ttu-id="81e47-116">在调用之后，预或后续处理脚本确定哪种部署状态 （安装、 导入、 删除、 卸载、 导入回滚，或安装回滚） 在运行通过检查环境变量 BTAD_ChangeRequestAction，BTAD_InstallMode，和 BTAD_HostClass 中, 所述[如何环境变量指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)。</span><span class="sxs-lookup"><span data-stu-id="81e47-116">Once invoked, a pre- or post-processing script determines which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running in by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode, and BTAD_HostClass, as described in [How Environment Variables Indicate Deployment State](../core/how-environment-variables-indicate-deployment-state.md).</span></span> <span data-ttu-id="81e47-117">引用的变量的信息，请参阅[前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="81e47-117">For reference information about the variables, see [Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md).</span></span>  
  
 <span data-ttu-id="81e47-118">将脚本添加到应用程序的说明，请参阅[如何添加预或对应用程序的后续处理脚本](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="81e47-118">For instructions on adding a script to an application, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81e47-119">如果要在脚本中包含命令行参数（如本主题稍后部分讨论），则必须使用 AddResource 命令来添加脚本。</span><span class="sxs-lookup"><span data-stu-id="81e47-119">If you want to include command-line arguments in a script, as discussed later in this topic, you must use the AddResource command to add the script.</span></span>  
  
## <a name="supported-script-file-extensions"></a><span data-ttu-id="81e47-120">支持的脚本文件扩展名</span><span class="sxs-lookup"><span data-stu-id="81e47-120">Supported script file extensions</span></span>  
 <span data-ttu-id="81e47-121">支持以下脚本文件扩展名：.com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf 和 .wsh。</span><span class="sxs-lookup"><span data-stu-id="81e47-121">The following script file extensions are supported: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf, and .wsh.</span></span> <span data-ttu-id="81e47-122">PATHEXT 环境变量中定义了此扩展名集合。</span><span class="sxs-lookup"><span data-stu-id="81e47-122">This set of extensions is defined in the PATHEXT environment variable.</span></span>  
  
## <a name="logging-errors"></a><span data-ttu-id="81e47-123">记录错误</span><span class="sxs-lookup"><span data-stu-id="81e47-123">Logging errors</span></span>  
 <span data-ttu-id="81e47-124">作为一种最佳实践，应该将每个脚本都配置为向文件中记录错误。</span><span class="sxs-lookup"><span data-stu-id="81e47-124">As a best practice, you should configure each script to log errors to a file.</span></span> <span data-ttu-id="81e47-125">这是因为 Windows Installer 不会记录脚本中生成的错误。</span><span class="sxs-lookup"><span data-stu-id="81e47-125">This is because Windows Installer does not log errors generated in the scripts.</span></span> <span data-ttu-id="81e47-126">如果脚本运行后出现需要解决的任何错误，则应该检查这些日志。</span><span class="sxs-lookup"><span data-stu-id="81e47-126">You should check these logs after the script runs for any errors that need to be addressed.</span></span>  
  
 <span data-ttu-id="81e47-127">为了帮助确定错误发生的时间，可以在日志文件中包含日期和时间。</span><span class="sxs-lookup"><span data-stu-id="81e47-127">To help you determine when the error occurred, you can include the date and time in the log file.</span></span>  
  
 <span data-ttu-id="81e47-128">使用以下代码可以指定一个日志文件，然后向其中记录一条错误。</span><span class="sxs-lookup"><span data-stu-id="81e47-128">Use the following code to specify a log file and then log an error to it.</span></span>  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 <span data-ttu-id="81e47-129">在以下示例中，如果未定义公钥标记，则会在指定的日志文件中记录一个条目。</span><span class="sxs-lookup"><span data-stu-id="81e47-129">In the following example, when the public key token is not defined, an entry is made in the specified log file.</span></span> <span data-ttu-id="81e47-130">在日志文件中，日期和时间与文本“Public key should be set in script”写在同一行中。</span><span class="sxs-lookup"><span data-stu-id="81e47-130">In the log file, the date and time is written in the same line as the text, "Public key should be set in script."</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 <span data-ttu-id="81e47-131">你还可以添加行`exit /b 1`到一个脚本来为 Windows 安装程序生成错误代码，这将导致其回滚。</span><span class="sxs-lookup"><span data-stu-id="81e47-131">You can also add the line `exit /b 1` to a script to generate an error code for Windows Installer, which will cause it to roll back.</span></span>  
  
 <span data-ttu-id="81e47-132">在以下示例中，如果未定义公钥标记，脚本会向 Windows Installer 返回一条错误，安装程序将会回滚。</span><span class="sxs-lookup"><span data-stu-id="81e47-132">In the following example, if the public key token has not been defined, the script will return an error to Windows Installer, and the installer will roll back.</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a><span data-ttu-id="81e47-133">在同一脚本中包含安装代码和清理代码</span><span class="sxs-lookup"><span data-stu-id="81e47-133">Including installation and cleanup code in the same script</span></span>  
 <span data-ttu-id="81e47-134">由于在安装和卸载过程中脚本的运行顺序相反，因此可以在同一脚本的条件语句中包含安装代码和清理代码。</span><span class="sxs-lookup"><span data-stu-id="81e47-134">Because scripts run in the opposite order during installation and uninstallation, you can include installation and cleanup code in the same script, inside a conditional statement.</span></span> <span data-ttu-id="81e47-135">例如，可以将安装代码放在检查安装模式的条件语句中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="81e47-135">For example, you can place the installation code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 <span data-ttu-id="81e47-136">可以将清理代码限定在检查安装模式的条件语句中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="81e47-136">You can qualify cleanup code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a><span data-ttu-id="81e47-137">传入命令行参数</span><span class="sxs-lookup"><span data-stu-id="81e47-137">Passing in command-line arguments</span></span>  
 <span data-ttu-id="81e47-138">在使用 BTSTask AddResource 命令将脚本添加到应用程序时，可以通过指定以下参数将命令行参数传递到脚本中。</span><span class="sxs-lookup"><span data-stu-id="81e47-138">You can pass command-line arguments into the script by specifying the following parameter when you use the BTSTask AddResource command to add the script to the application.</span></span> <span data-ttu-id="81e47-139">执行此操作时，参数会在调用脚本时传递到脚本中。</span><span class="sxs-lookup"><span data-stu-id="81e47-139">When you do this, the arguments are passed to the script when the script is invoked.</span></span>  
  
 <span data-ttu-id="81e47-140">**/Property:Args =**"*自变量列表*"</span><span class="sxs-lookup"><span data-stu-id="81e47-140">**/Property:Args=**"*argument list*"</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81e47-141">如果应用程序中有多个预处理脚本或后处理脚本，它们不会按特定的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="81e47-141">If you have multiple pre- or post-processing scripts in and application, they are run in no particular order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81e47-142">不要在脚本中使用 BTSTask 命令，特别是那些在导入过程中运行的命令，因为脚本与导入未登记在同一个事务中。</span><span class="sxs-lookup"><span data-stu-id="81e47-142">You should not use BTSTask commands in scripts, especially those that run during import, because scripts are not enlisted in the same transaction as an import.</span></span>  
  
 <span data-ttu-id="81e47-143">有关使用 AddResource 命令将脚本添加到应用程序的说明，请参阅[AddResource 命令： 预处理脚本](../core/addresource-command-preprocessing-script.md)。</span><span class="sxs-lookup"><span data-stu-id="81e47-143">For instructions on using the AddResource command to add a script to an application, see [AddResource Command: Preprocessing Script](../core/addresource-command-preprocessing-script.md).</span></span> <span data-ttu-id="81e47-144">另请参阅[AddResource 命令： 后处理脚本](../core/addresource-command-postprocessing-script.md)</span><span class="sxs-lookup"><span data-stu-id="81e47-144">Also see [AddResource Command: Postprocessing Script](../core/addresource-command-postprocessing-script.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e47-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e47-145">See Also</span></span>  
 <span data-ttu-id="81e47-146">[前期和后期处理脚本用于自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="81e47-146">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 [<span data-ttu-id="81e47-147">模板 （应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="81e47-147">Template (Application Deployment Sample)</span></span>](../core/template-application-deployment-sample.md)