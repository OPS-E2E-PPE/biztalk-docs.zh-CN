---
title: CreateApp （应用程序部署示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce2b895b11a8a2ad0fc6b863d3cd67a20c5c1007
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354182"
---
# <a name="createapp-application-deployment-sample"></a>CreateApp （应用程序部署示例）
本主题说明如何使用 CreateApp 示例，演示了如何使用 BTSTask 命令行工具部署和取消部署 BizTalk 应用程序。 如本示例中包含的脚本可用于自动执行夜间生成过程来部署和取消部署 BizTalk 应用程序。  
  
> [!IMPORTANT]
>  始终应编写你的部署脚本在无提示模式下运行。 如果不这样做，对话框将显示要求用户输入。 这将停止部署过程，直到对话框的手动关闭，这可能导致导入过程挂起。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 该示例包括自动执行应用程序部署任务的脚本。 若要执行这些任务，则运行生成 BizTalk 项目和文件的脚本。 然后运行生成两个 BizTalk 应用程序.msi 文件 – 一个包含的所有包含应用程序中的只有一个程序集在应用程序，另一个项目的.msi 文件的脚本。 接下来您运行的脚本使用某一.msi 文件导入到 BizTalk 组的应用程序并安装到本地计算机上的应用程序。 在安装期间，应用程序中包含的预处理脚本创建应用程序使用的文件夹，并其操作记录到文件。 最后，运行一个脚本来删除并卸载该应用程序。 卸载期间，应用程序中包含的预处理脚本中删除的文件和在安装期间创建的文件夹和其操作记录到文件。  
  
 此示例随附的脚本如下：  
  
-   **Build.bat。** 生成一个密钥文件、 生成 Visual Studio 中的项目并对.dll 文件进行签名。  
  
-   **CreateFullAndPartialMSI.bat.** 在顺序中采用以下操作：  
  
    1.  使用 BTSTask [AddApp 命令](../core/addapp-command.md)创建应用程序。  
  
    2.  使用 BTSTask [AddResource 命令](../core/addresource-command.md)将 Build.bat 生成的以及其他资源添加到应用程序三个 BizTalk 程序集。  
  
    3.  使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)将导出到某一.msi 文件的应用程序的项目名为 CreateApplicationSample.msi。  
  
    4.  使用 BTSTask [ListApp 命令](../core/listapp-command.md)以生成名为 AppManifest.xml，其中列出了在应用程序中包含的项目的所有应用程序清单。  
  
    5.  使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)仅将业务流程程序集导出到名为 CreateApplicationSamplePartial.msi 的.msi 文件。 通过为 ResourceSpec 参数提供 ResourceSpecPartial.xml 执行此操作。 ResouceSpecPartial.xml 是本示例提供的 ResourceSpecComplete.xml 的已编辑的版本。 已编辑此文件，使其包含到只有业务流程程序集的引用。 如果使用此参数提供，BTSTask 导出仅列出在 ResourceSpecPartial.xml 文件 – 这种情况下，业务流程程序集的项目。  
  
    6.  从组的 BizTalk 管理数据库中删除应用程序。  
  
-   **CreateNewAppFromMSI.bat.** 使用 CreateFullAndPartialMSI.bat 生成的： CreateApplicationSample.msi 安装在本地计算机上名为 CreateApplicationSample 的应用程序，以及将应用程序导入 BizTalk 组。 在安装期间，PreProcScript.bat 将自动运行，如下文所述。  
  
-   **RemoveApp.bat.** 在顺序中采用以下操作：  
  
    1.  使用 BTSTask [RemoveApp 命令](../core/removeapp-command.md)从该组的 BizTalk 管理数据库中删除 CreateApplicationSample 应用程序。  
  
    2.  使用 BTSTask [UninstallApp 命令](../core/uninstallapp-command.md)若要从本地计算机上卸载 CreateApplicationSample 应用程序。 在安装期间，PreProcScript.bat 自动运行，如下所述。  
  
-   **PreProcScript.bat.** 将执行以下操作：  
  
    -   每次运行时，设置已由用户提供的程序集的公钥标记。  
  
    -   应用程序在安装期间，创建 CreateApplicationSample 应用程序将用于包含消息的以下文件夹：  
  
         C:\CreateApplicationSample\Out  
  
         C:\CreateApplicationSample\In  
  
    -   在应用程序卸载期间删除的文件和在安装期间创建的文件夹。 此外从全局程序集缓存 (GAC) 卸载安装期间在 GAC 中安装任何程序集和其操作记录到文件。 若要从 GAC 卸载程序集，它指由用户提供的公钥标记。  
  
    -   安装和卸载，期间创建的日志文件中的以下位置：  
  
         C:\ScriptLog.txt  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 您可以在下的以下文件夹中找到示例文件*\<示例路径\>* \Application 部署\\:  
  
-   CreateApp （文件夹）  
  
    -   Build.bat  
  
    -   CreateFullAndPartialMSI.bat  
  
    -   CreateNewAppFromMSI.bat  
  
    -   RemoveApp.bat  
  
-   CreateApp\Bindings （文件夹）  
  
    -   CreateApplicationSampleBindings.xml  
  
-   CreateApp\Dlls (Folder)  
  
    -   Empty  
  
-   CreateApp\ResourceSpecs （文件夹）  
  
    -   ResourceSpecPartial.xml  
  
    -   ResourceSpecComplete.xml  
  
-   CreateApp\Scripts (Folder)  
  
    -   PreProcScript.bat  
  
-   CreateApp\HelloApplicationDeployment (Folder)  
  
    -   HelloApplicationDeployment.suo  
  
    -   HelloApplicationDeployment.sln  
  
-   CreateApp\HelloApplicationDeployment\Maps (Folder)  
  
    -   POToInvoice.btm  
  
    -   Maps.btproj  
  
-   CreateApp\HelloApplicationDeployment\Orchestrations (Folder)  
  
    -   Orchestrations.btproj  
  
    -   HelloOrchestration.odx  
  
-   CreateApp\HelloApplicationDeployment\Schemas (Folder)  
  
    -   Schemas.btproj  
  
    -   POSchema.xsd  
  
    -   InvoiceSchema.xsd  
  
## <a name="how-to-use-this-sample"></a>如何使用此示例  
 使用以下过程使用此示例。  
  
### <a name="to-use-the-sample"></a>若要使用的示例  
  
1.  运行 Build.bat。 这将生成一个密钥文件、 HelloApplicationDeployment 文件夹下生成项目、 对生成的.dll 文件进行签名和放置到 Dlls 文件夹中。  
  
2.  打开 PreProcScript.bat 文件，位于 CreateApp\Scripts 文件夹中。 在以下代码行，删除 REM 并提供该程序集的公钥标记：  
  
     **REM set PublicKeyToken=**  
  
     例如：  
  
     **set PublicKeyToken=1234a5b6c1234567**  
  
3.  运行 CreateFullAndPartialMSI.bat。 这将创建两个应用程序.msi 文件： CreateApplicationSample.msi 和 CreateApplicationSamplePartial.msi。  
  
4.  运行 CreateNewAppFromMSI.bat。 此操作将 CreateApplicationSample 应用程序导入到 BizTalk 组，并将其安装在本地计算机上。  
  
5.  检查位于 C:\ScriptLog.txt 以验证该脚本已记录其安装操作的脚本日志文件。  
  
6.  验证 CreateApplicationSample 应用程序显示在 BizTalk Server 管理控制台并添加或删除程序。  
  
7.  运行 RemoveApp.bat。 这将从 BizTalk 管理数据库中删除 CreateApplicationSample，并从本地计算机进行卸载。  
  
8.  检查 C:\ScriptLog.txt 以验证该脚本已记录其卸载操作所位于的脚本日志文件。 它们应显示在安装过程中更早版本，记录的安装操作之后。  
  
9. 验证 CreateApplicationSample 应用程序不会再出现在 BizTalk Server 管理控制台或添加或删除程序。  
  
10. 验证在安装期间创建的文件夹已被删除。  
  
11. 验证已从 GAC 卸载了程序集。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)