---
title: 创建的预处理或后处理脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20c95273cc0140da79ac1972be2071f40e0c348
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354101"
---
# <a name="creating-a-pre--or-post-processing-script"></a><span data-ttu-id="93482-102">创建预处理或后处理脚本</span><span class="sxs-lookup"><span data-stu-id="93482-102">Creating a Pre- or Post-processing Script</span></span>
<span data-ttu-id="93482-103">可以创建一个脚本来执行操作，当应用程序部署，并定义及其在部署过程中运行时。</span><span class="sxs-lookup"><span data-stu-id="93482-103">You can create a script to perform actions when an application is deployed, and then define when it will run during the deployment process.</span></span> <span data-ttu-id="93482-104">可以在同一个脚本中，包括安装和清理代码，使用环境变量来分隔代码。</span><span class="sxs-lookup"><span data-stu-id="93482-104">You can include both installation and cleanup code in the same script, using environment variables to delimit the code.</span></span> <span data-ttu-id="93482-105">此外可以将命令行参数传递到脚本。</span><span class="sxs-lookup"><span data-stu-id="93482-105">You can also pass command-line arguments into the script.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="93482-106">您应始终编写脚本用于在无提示模式下的生产系统。</span><span class="sxs-lookup"><span data-stu-id="93482-106">You should always write scripts intended for production systems in silent mode.</span></span> <span data-ttu-id="93482-107">这是因为等待用户输入的脚本将导致 BizTalk 数据库锁定，并且收到输入之前无法访问。</span><span class="sxs-lookup"><span data-stu-id="93482-107">This is because a script waiting for user input will cause the BizTalk databases to become locked and inaccessible until the input is received.</span></span>  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a><span data-ttu-id="93482-108">指定脚本在部署期间的运行时</span><span class="sxs-lookup"><span data-stu-id="93482-108">Specifying when a script will run during deployment</span></span>  
 <span data-ttu-id="93482-109">您指定在脚本将运行时通过将其添加为 system.biztalk: preprocessingscript （预处理脚本） 的脚本添加到应用程序或 system.biztalk: postprocessingscript （后处理脚本）。</span><span class="sxs-lookup"><span data-stu-id="93482-109">You specify when a script will run when you add the script to an application by adding it as either a System.BizTalk:PreProcessingScript (pre-processing script) or a System.BizTalk:PostProcessingScript (post-processing script).</span></span>  
  
 <span data-ttu-id="93482-110">预处理和后处理脚本运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="93482-110">Pre- and post-processing scripts run as follows:</span></span>  
  
- <span data-ttu-id="93482-111">预处理脚本在导入或安装过程开始时运行。</span><span class="sxs-lookup"><span data-stu-id="93482-111">Pre-processing scripts run at the beginning of the import or installation process.</span></span>  
  
- <span data-ttu-id="93482-112">在导入或安装过程结束时，运行后续处理脚本。</span><span class="sxs-lookup"><span data-stu-id="93482-112">Post-processing scripts run at the end of the import or installation process.</span></span>  
  
- <span data-ttu-id="93482-113">在卸载，所有脚本都运行在安装过程中的都运行顺序的相反顺序。</span><span class="sxs-lookup"><span data-stu-id="93482-113">During uninstallation, all scripts run in the opposite order that they run during installation.</span></span> <span data-ttu-id="93482-114">因此，后处理脚本运行卸载和预处理脚本在卸载结束的开始处。</span><span class="sxs-lookup"><span data-stu-id="93482-114">Therefore, post-processing scripts run at the beginning of uninstallation and pre-processing scripts at the end of uninstallation.</span></span>  
  
- <span data-ttu-id="93482-115">如果应用安装失败，脚本将按相反的顺序调用与相应的回滚操作。</span><span class="sxs-lookup"><span data-stu-id="93482-115">If an installation fails, scripts are called in reverse order with the appropriate rollback action.</span></span>  
  
  <span data-ttu-id="93482-116">在调用之后，预处理或后处理脚本确定的部署状态 （安装、 导入、 删除、 卸载、 导入回滚或安装回滚） 通过检查环境变量 BTAD_ChangeRequestAction、 BTAD_InstallMode，运行和 BTAD_HostClass，如中所述[如何环境变量指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)。</span><span class="sxs-lookup"><span data-stu-id="93482-116">Once invoked, a pre- or post-processing script determines which deployment state (install, import, delete, uninstall, import rollback, or install rollback) it is running in by checking the environment variables BTAD_ChangeRequestAction, BTAD_InstallMode, and BTAD_HostClass, as described in [How Environment Variables Indicate Deployment State](../core/how-environment-variables-indicate-deployment-state.md).</span></span> <span data-ttu-id="93482-117">有关变量的参考信息，请参阅[预处理和后处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="93482-117">For reference information about the variables, see [Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md).</span></span>  
  
  <span data-ttu-id="93482-118">将脚本添加到应用程序的说明，请参阅[How to Add 的预处理或后处理脚本保存到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="93482-118">For instructions on adding a script to an application, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93482-119">如果你想要包括命令行自变量在脚本中，如本主题后面所述，必须使用 AddResource 命令来添加脚本。</span><span class="sxs-lookup"><span data-stu-id="93482-119">If you want to include command-line arguments in a script, as discussed later in this topic, you must use the AddResource command to add the script.</span></span>  
  
## <a name="supported-script-file-extensions"></a><span data-ttu-id="93482-120">支持的脚本文件扩展名</span><span class="sxs-lookup"><span data-stu-id="93482-120">Supported script file extensions</span></span>  
 <span data-ttu-id="93482-121">支持以下脚本文件扩展名：.com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf 和.wsh。</span><span class="sxs-lookup"><span data-stu-id="93482-121">The following script file extensions are supported: .com, .exe, .bat, .cmd, .vbs, .vbe, .js, .jse, .wsf, and .wsh.</span></span> <span data-ttu-id="93482-122">这组扩展定义 PATHEXT 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="93482-122">This set of extensions is defined in the PATHEXT environment variable.</span></span>  
  
## <a name="logging-errors"></a><span data-ttu-id="93482-123">记录错误</span><span class="sxs-lookup"><span data-stu-id="93482-123">Logging errors</span></span>  
 <span data-ttu-id="93482-124">作为最佳做法，应配置每个脚本以将错误记录到一个文件。</span><span class="sxs-lookup"><span data-stu-id="93482-124">As a best practice, you should configure each script to log errors to a file.</span></span> <span data-ttu-id="93482-125">这是因为 Windows 安装程序不会记录在脚本中生成的错误。</span><span class="sxs-lookup"><span data-stu-id="93482-125">This is because Windows Installer does not log errors generated in the scripts.</span></span> <span data-ttu-id="93482-126">该脚本运行的任何错误，必须先解决后，应检查这些日志。</span><span class="sxs-lookup"><span data-stu-id="93482-126">You should check these logs after the script runs for any errors that need to be addressed.</span></span>  
  
 <span data-ttu-id="93482-127">若要帮助你确定发生错误时，可以在日志文件中包含的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="93482-127">To help you determine when the error occurred, you can include the date and time in the log file.</span></span>  
  
 <span data-ttu-id="93482-128">使用以下代码来指定日志文件，然后向其记录错误。</span><span class="sxs-lookup"><span data-stu-id="93482-128">Use the following code to specify a log file and then log an error to it.</span></span>  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 <span data-ttu-id="93482-129">在以下示例中，未定义公钥标记，生成一个条目是在指定的日志文件中。</span><span class="sxs-lookup"><span data-stu-id="93482-129">In the following example, when the public key token is not defined, an entry is made in the specified log file.</span></span> <span data-ttu-id="93482-130">在日志文件中，用文本的同一行编写的日期和时间，"公共密钥应设置在脚本中。"</span><span class="sxs-lookup"><span data-stu-id="93482-130">In the log file, the date and time is written in the same line as the text, "Public key should be set in script."</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 <span data-ttu-id="93482-131">您还可以添加行`exit /b 1`到脚本中以便为 Windows 安装程序生成一个错误代码，这将导致其回滚。</span><span class="sxs-lookup"><span data-stu-id="93482-131">You can also add the line `exit /b 1` to a script to generate an error code for Windows Installer, which will cause it to roll back.</span></span>  
  
 <span data-ttu-id="93482-132">在下面的示例中，如果尚未定义公钥标记，该脚本将向 Windows 安装程序中，返回错误并且安装程序将回滚。</span><span class="sxs-lookup"><span data-stu-id="93482-132">In the following example, if the public key token has not been defined, the script will return an error to Windows Installer, and the installer will roll back.</span></span>  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a><span data-ttu-id="93482-133">在同一个脚本中包括安装和清理代码</span><span class="sxs-lookup"><span data-stu-id="93482-133">Including installation and cleanup code in the same script</span></span>  
 <span data-ttu-id="93482-134">因为脚本相反的顺序安装和卸载期间运行，可以在同一个脚本中的条件语句中包含安装代码和清理代码。</span><span class="sxs-lookup"><span data-stu-id="93482-134">Because scripts run in the opposite order during installation and uninstallation, you can include installation and cleanup code in the same script, inside a conditional statement.</span></span> <span data-ttu-id="93482-135">例如，可以将检查安装模式，如下所示的条件语句中的安装代码：</span><span class="sxs-lookup"><span data-stu-id="93482-135">For example, you can place the installation code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 <span data-ttu-id="93482-136">你可以清理代码限定在检查安装模式，如下所示的条件语句中：</span><span class="sxs-lookup"><span data-stu-id="93482-136">You can qualify cleanup code within a conditional statement that checks for the installation mode, as follows:</span></span>  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a><span data-ttu-id="93482-137">在命令行参数中传递</span><span class="sxs-lookup"><span data-stu-id="93482-137">Passing in command-line arguments</span></span>  
 <span data-ttu-id="93482-138">通过使用 BTSTask AddResource 命令将脚本添加到应用程序时指定以下参数，可以将传入脚本的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="93482-138">You can pass command-line arguments into the script by specifying the following parameter when you use the BTSTask AddResource command to add the script to the application.</span></span> <span data-ttu-id="93482-139">当执行此操作时，参数传递到脚本时调用相应的脚本。</span><span class="sxs-lookup"><span data-stu-id="93482-139">When you do this, the arguments are passed to the script when the script is invoked.</span></span>  
  
 <span data-ttu-id="93482-140">**/Property:Args=**"*argument list*"</span><span class="sxs-lookup"><span data-stu-id="93482-140">**/Property:Args=**"*argument list*"</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93482-141">如果有多个中的预处理或后处理脚本和应用程序时，不按特定顺序运行。</span><span class="sxs-lookup"><span data-stu-id="93482-141">If you have multiple pre- or post-processing scripts in and application, they are run in no particular order.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="93482-142">不应在脚本中，尤其是那些以运行导入期间，因为脚本未登记与导入在同一事务中使用 BTSTask 命令。</span><span class="sxs-lookup"><span data-stu-id="93482-142">You should not use BTSTask commands in scripts, especially those that run during import, because scripts are not enlisted in the same transaction as an import.</span></span>  
  
 <span data-ttu-id="93482-143">有关使用 AddResource 命令将脚本添加到应用程序的说明，请参阅[AddResource 命令：预处理脚本](../core/addresource-command-preprocessing-script.md)。</span><span class="sxs-lookup"><span data-stu-id="93482-143">For instructions on using the AddResource command to add a script to an application, see [AddResource Command: Preprocessing Script](../core/addresource-command-preprocessing-script.md).</span></span> <span data-ttu-id="93482-144">另请参阅[AddResource 命令：后续处理脚本](../core/addresource-command-postprocessing-script.md)</span><span class="sxs-lookup"><span data-stu-id="93482-144">Also see [AddResource Command: Postprocessing Script](../core/addresource-command-postprocessing-script.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93482-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="93482-145">See Also</span></span>  
 <span data-ttu-id="93482-146">[使用预处理和后处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="93482-146">[Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md) </span></span>  
 [<span data-ttu-id="93482-147">模板（应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="93482-147">Template (Application Deployment Sample)</span></span>](../core/template-application-deployment-sample.md)