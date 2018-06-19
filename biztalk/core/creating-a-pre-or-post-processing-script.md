---
title: 创建预或操作的后续处理脚本 |Microsoft 文档
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
ms.openlocfilehash: 532c730d5a654512610a37c9dac783fbc6a76d6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239293"
---
# <a name="creating-a-pre--or-post-processing-script"></a>创建预处理或后处理脚本
您可以在布署应用程序时创建脚本来执行操作，然后定义在部署过程中何时运行该脚本。 同一脚本中可以同时包含安装和清理代码，之间用环境变量分隔。 也可以向脚本中传递命令行参数。  
  
> [!CAUTION]
>  您始终应以无提示模式编写用于生产系统的脚本。 这是因为等待用户输入的脚本会导致 BizTalk 数据库锁定和无法访问，直到收到输入时为止。  
  
## <a name="specifying-when-a-script-will-run-during-deployment"></a>指定脚本在部署期间何时运行  
 通过将脚本作为 System.BizTalk:PreProcessingScript（预处理脚本）或 System.BizTalk:PostProcessingScript（后处理脚本）添加到应用程序，可以指定何时运行该脚本。  
  
 预处理脚本和后处理脚本以如下方式运行：  
  
-   预处理脚本在导入或安装过程开始时运行。  
  
-   后处理脚本在导入或安装过程结束时运行。  
  
-   在卸载过程中，所有脚本的运行顺序与安装过程中的运行顺序相反。 因此，后处理脚本在卸载开始时运行，预处理脚本在卸载结束时运行。  
  
-   如果安装失败，则会使用相应的回滚操作以相反顺序调用脚本。  
  
 在调用之后，预或后续处理脚本确定哪种部署状态 （安装、 导入、 删除、 卸载、 导入回滚，或安装回滚） 在运行通过检查环境变量 BTAD_ChangeRequestAction，BTAD_InstallMode，和 BTAD_HostClass 中, 所述[如何环境变量指示部署状态](../core/how-environment-variables-indicate-deployment-state.md)。 引用的变量的信息，请参阅[前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md)。  
  
 将脚本添加到应用程序的说明，请参阅[如何添加预或对应用程序的后续处理脚本](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。  
  
> [!NOTE]
>  如果要在脚本中包含命令行参数（如本主题稍后部分讨论），则必须使用 AddResource 命令来添加脚本。  
  
## <a name="supported-script-file-extensions"></a>支持的脚本文件扩展名  
 支持以下脚本文件扩展名：.com、.exe、.bat、.cmd、.vbs、.vbe、.js、.jse、.wsf 和 .wsh。 PATHEXT 环境变量中定义了此扩展名集合。  
  
## <a name="logging-errors"></a>记录错误  
 作为一种最佳实践，应该将每个脚本都配置为向文件中记录错误。 这是因为 Windows Installer 不会记录脚本中生成的错误。 如果脚本运行后出现需要解决的任何错误，则应该检查这些日志。  
  
 为了帮助确定错误发生的时间，可以在日志文件中包含日期和时间。  
  
 使用以下代码可以指定一个日志文件，然后向其中记录一条错误。  
  
 `Set LogFile=<full path of log file>`  
  
 `…`  
  
 `echo %DATE% %TIME% <text> >> %LogFile%`  
  
 在以下示例中，如果未定义公钥标记，则会在指定的日志文件中记录一个条目。 在日志文件中，日期和时间与文本“Public key should be set in script”写在同一行中。  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 你还可以添加行`exit /b 1`到一个脚本来为 Windows 安装程序生成错误代码，这将导致其回滚。  
  
 在以下示例中，如果未定义公钥标记，脚本会向 Windows Installer 返回一条错误，安装程序将会回滚。  
  
 `set LogFile=C:\ScriptLog.txt`  
  
 `set PublicKeyToken=e5fd0ea4ecd37420`  
  
 `if not defined PublicKeyToken (`  
  
 `echo %DATE% %TIME% Public key should be set in script >> %LogFile%`  
  
 `exit /b 1`  
  
## <a name="including-installation-and-cleanup-code-in-the-same-script"></a>在同一脚本中包含安装代码和清理代码  
 由于在安装和卸载过程中脚本的运行顺序相反，因此可以在同一脚本的条件语句中包含安装代码和清理代码。 例如，可以将安装代码放在检查安装模式的条件语句中，如下所示：  
  
```  
  
%BTAD_ChangeRequestAction%=Update AND %BTAD_InstallMode%=Install  
  
```  
  
 可以将清理代码限定在检查安装模式的条件语句中，如下所示：  
  
```  
  
%BTAD_ChangeRequestAction%=Delete AND %BTAD_InstallMode%=Uninstall  
  
```  
  
## <a name="passing-in-command-line-arguments"></a>传入命令行参数  
 在使用 BTSTask AddResource 命令将脚本添加到应用程序时，可以通过指定以下参数将命令行参数传递到脚本中。 执行此操作时，参数会在调用脚本时传递到脚本中。  
  
 **/Property:Args =**"*自变量列表*"  
  
> [!NOTE]
>  如果应用程序中有多个预处理脚本或后处理脚本，它们不会按特定的顺序运行。  
  
> [!IMPORTANT]
>  不要在脚本中使用 BTSTask 命令，特别是那些在导入过程中运行的命令，因为脚本与导入未登记在同一个事务中。  
  
 有关使用 AddResource 命令将脚本添加到应用程序的说明，请参阅[AddResource 命令： 预处理脚本](../core/addresource-command-preprocessing-script.md)。 另请参阅[AddResource 命令： 后处理脚本](../core/addresource-command-postprocessing-script.md)  
  
## <a name="see-also"></a>另请参阅  
 [前期和后期处理脚本用于自定义应用程序部署](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)   
 [模板 （应用程序部署示例）](../core/template-application-deployment-sample.md)