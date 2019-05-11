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
# <a name="creating-a-pre--or-post-processing-script"></a>创建预处理或后处理脚本
可以创建一个脚本来执行操作，当应用程序部署，并定义及其在部署过程中运行时。 可以在同一个脚本中，包括安装和清理代码，使用环境变量来分隔代码。 此外可以将命令行参数传递到脚本。  
  
> [!CAUTION]
>  您应始终编写脚本用于在无提示模式下的生产系统。 这是因为等待用户输入的脚本将导致 BizTalk 数据库锁定，并且收到输入之前无法访问。  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a>指定脚本在部署期间的运行时  
 您指定在脚本将运行时通过将其添加为 system.biztalk: preprocessingscript （预处理脚本） 的脚本添加到应用程序或 system.biztalk: postprocessingscript （后处理脚本）。  
  
 预处理和后处理脚本运行，如下所示：  
  
- 预处理脚本在导入或安装过程开始时运行。  
  
- 在导入或安装过程结束时，运行后续处理脚本。  
  
- 在卸载，所有脚本都运行在安装过程中的都运行顺序的相反顺序。 因此，后处理脚本运行卸载和预处理脚本在卸载结束的开始处。  
  
- 如果应用安装失败，脚本将按相反的顺序调用与相应的回滚操作。  
  
  在调用之后，预处理或后处理脚本确定的部署状态 （安装、 导入、 删除、 卸载、 导入回滚或安装回滚） 通过检查环境变量 BTAD_ChangeRequestAction、 BTAD_InstallMode，运行和 BTAD_HostClass，如中所述[如何环境变量指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)。 有关变量的参考信息，请参阅[预处理和后处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)。  
  
  将脚本添加到应用程序的说明，请参阅[How to Add 的预处理或后处理脚本保存到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。  
  
> [!NOTE]
>  如果你想要包括命令行自变量在脚本中，如本主题后面所述，必须使用 AddResource 命令来添加脚本。  
  
## <a name="supported-script-file-extensions"></a>支持的脚本文件扩展名  
 支持以下脚本文件扩展名：.com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf 和.wsh。 这组扩展定义 PATHEXT 环境变量中。  
  
## <a name="logging-errors"></a>记录错误  
 作为最佳做法，应配置每个脚本以将错误记录到一个文件。 这是因为 Windows 安装程序不会记录在脚本中生成的错误。 该脚本运行的任何错误，必须先解决后，应检查这些日志。  
  
 若要帮助你确定发生错误时，可以在日志文件中包含的日期和时间。  
  
 使用以下代码来指定日志文件，然后向其记录错误。  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 在以下示例中，未定义公钥标记，生成一个条目是在指定的日志文件中。 在日志文件中，用文本的同一行编写的日期和时间，"公共密钥应设置在脚本中。"  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 您还可以添加行`exit /b 1`到脚本中以便为 Windows 安装程序生成一个错误代码，这将导致其回滚。  
  
 在下面的示例中，如果尚未定义公钥标记，该脚本将向 Windows 安装程序中，返回错误并且安装程序将回滚。  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a>在同一个脚本中包括安装和清理代码  
 因为脚本相反的顺序安装和卸载期间运行，可以在同一个脚本中的条件语句中包含安装代码和清理代码。 例如，可以将检查安装模式，如下所示的条件语句中的安装代码：  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 你可以清理代码限定在检查安装模式，如下所示的条件语句中：  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a>在命令行参数中传递  
 通过使用 BTSTask AddResource 命令将脚本添加到应用程序时指定以下参数，可以将传入脚本的命令行参数。 当执行此操作时，参数传递到脚本时调用相应的脚本。  
  
 **/Property:Args=**"*argument list*"  
  
> [!NOTE]
>  如果有多个中的预处理或后处理脚本和应用程序时，不按特定顺序运行。  
  
> [!IMPORTANT]
>  不应在脚本中，尤其是那些以运行导入期间，因为脚本未登记与导入在同一事务中使用 BTSTask 命令。  
  
 有关使用 AddResource 命令将脚本添加到应用程序的说明，请参阅[AddResource 命令：预处理脚本](../core/addresource-command-preprocessing-script.md)。 另请参阅[AddResource 命令：后续处理脚本](../core/addresource-command-postprocessing-script.md)  
  
## <a name="see-also"></a>请参阅  
 [使用预处理和后处理脚本自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [模板（应用程序部署示例）](../core/template-application-deployment-sample.md)