---
title: "CreateApp （应用程序部署示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 842683d2eec04d77bad2b7726af0d687fae12884
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="createapp-application-deployment-sample"></a>CreateApp（应用程序部署示例）
本主题介绍如何使用 CreateApp 示例，该示例演示如何使用 BTSTask 命令行工具部署和取消部署 BizTalk 应用程序。 您可以使用本示例中包含的脚本等自动执行夜间生成过程，来部署和取消部署 BizTalk 应用程序。  
  
> [!IMPORTANT]
>  应始终将部署脚本编写为在静默模式下运行。 否则，将显示要求用户输入的对话框。 这将停止部署过程，直到您手动关闭此对话框为止，并可能导致导入过程挂起。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例包含用于自动执行应用程序部署任务的脚本。 若要执行这些任务，请运行生成 BizTalk 项目和文件的脚本。 然后运行生成两个 BizTalk 应用程序 .msi 文件的脚本 – 一个 .msi 文件包含应用程序中的所有项目 ， 而另一个 .msi 文件只包含应用程序中的一个程序集 。 接着，运行使用 .msi 文件将应用程序导入某一 BizTalk 组并在本地计算机上安装该应用程序的脚本。 安装期间，该应用程序中包含的预处理脚本将创建由该应用程序使用的文件夹，并将其操作记录到文件中。 最后，运行删除并卸载该应用程序的脚本。 卸载期间，该应用程序中包含的预处理脚本将删除在安装期间创建的文件和文件夹，并将其操作记录到文件中。  
  
 下面列出了本示例中包含的脚本：  
  
-   **Build.bat。** 生成密钥文件，在 Visual Studio 中生成项目并对 .dll 文件签名。  
  
-   **CreateFullAndPartialMSI.bat。** 按顺序执行下列操作：  
  
    1.  使用 BTSTask [AddApp 命令](../core/addapp-command.md)创建应用程序。  
  
    2.  使用 BTSTask [AddResource 命令](../core/addresource-command.md)将添加到应用程序三 BizTalk 程序集生成 Build.bat 以及其他资源。  
  
    3.  使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)将导出到.msi 文件的应用程序的项目名为 CreateApplicationSample.msi。  
  
    4.  使用 BTSTask [ListApp 命令](../core/listapp-command.md)来生成名为 AppManifest.xml，列出所有包含在应用程序的项目的应用程序清单。  
  
    5.  使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)导出到名为 CreateApplicationSamplePartial.msi.msi 文件业务流程程序集的仅。 该操作是通过向 ResourceSpec 参数提供 ResourceSpecPartial.xml 执行的。 ResouceSpecPartial.xml 是随本示例提供的 ResourceSpecComplete.xml 的已编辑版本。 已对该文件进行编辑，使其仅包含对业务流程程序集的引用。 使用此参数时 ， BTSTask 仅导出在 ResourceSpecPartial.xml 文件中列出的项目 – 在本示例中为业务流程程序集 。  
  
    6.  从该组的 BizTalk 管理数据库中删除此应用程序。  
  
-   **CreateNewAppFromMSI.bat。** 使用 CreateFullAndPartialMSI.bat 生成的 CreateApplicationSample.msi 在本地计算机上安装名为 CreateApplicationSample 的应用程序，并将该应用程序导入到 BizTalk 组。 安装期间，PreProcScript.bat 将自动运行，如后文所述。  
  
-   **RemoveApp.bat。** 按顺序执行下列操作：  
  
    1.  使用 BTSTask [RemoveApp 命令](../core/removeapp-command.md)若要从组 BizTalk 管理数据库中删除 CreateApplicationSample 应用程序。  
  
    2.  使用 BTSTask [UninstallApp 命令](../core/uninstallapp-command.md)以从本地计算机上卸载 CreateApplicationSample 应用程序。 安装期间，PreProcScript.bat 将自动运行，如下文所述。  
  
-   **PreProcScript.bat。** 执行下列操作：  
  
    -   每次运行时，设置用户提供的程序集的公钥标记。  
  
    -   在应用程序安装期间，创建 CreateApplicationSample 应用程序用于包含消息的下列文件夹：  
  
         C:\CreateApplicationSample\Out  
  
         C:\CreateApplicationSample\In  
  
    -   在应用程序卸载期间，删除在安装期间创建的文件和文件夹。 同时，还将从全局程序集缓存 (GAC) 卸载安装期间在 GAC 中安装的任意程序集，并将其操作记录到文件中。 若要从 GAC 卸载程序集，该脚本引用用户提供的公钥标记。  
  
    -   在安装和卸载期间，将在以下位置创建日志文件：  
  
         C:\ScriptLog.txt  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 你可以在下的以下文件夹中找到示例文件*\<示例路径\>*\Application 部署\\:  
  
-   CreateApp（文件夹）  
  
    -   Build.bat  
  
    -   CreateFullAndPartialMSI.bat  
  
    -   CreateNewAppFromMSI.bat  
  
    -   RemoveApp.bat  
  
-   CreateApp\Bindings（文件夹）  
  
    -   CreateApplicationSampleBindings.xml  
  
-   CreateApp\Dlls（文件夹）  
  
    -   Empty  
  
-   CreateApp\ResourceSpecs（文件夹）  
  
    -   ResourceSpecPartial.xml  
  
    -   ResourceSpecComplete.xml  
  
-   CreateApp\Scripts（文件夹）  
  
    -   PreProcScript.bat  
  
-   CreateApp\HelloApplicationDeployment（文件夹）  
  
    -   HelloApplicationDeployment.suo  
  
    -   HelloApplicationDeployment.sln  
  
-   CreateApp\HelloApplicationDeployment\Maps（文件夹）  
  
    -   POToInvoice.btm  
  
    -   Maps.btproj  
  
-   CreateApp\HelloApplicationDeployment\Orchestrations（文件夹）  
  
    -   Orchestrations.btproj  
  
    -   HelloOrchestration.odx  
  
-   CreateApp\HelloApplicationDeployment\Schemas（文件夹）  
  
    -   Schemas.btproj  
  
    -   POSchema.xsd  
  
    -   InvoiceSchema.xsd  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 请按照以下步骤使用本示例。  
  
### <a name="to-use-the-sample"></a>使用本示例  
  
1.  运行 Build.bat。 此操作将生成一个密钥文件、在 HelloApplicationDeployment 文件夹下生成项目、对生成的 .dll 文件签名并将 .dll 文件放置到 Dlls 文件夹中。  
  
2.  打开 PreProcScript.bat 文件，该文件位于 CreateApp\Scripts 文件夹中。 在以下代码行中，删除 REM 并提供程序集的公钥标记：  
  
     **REM 设置 PublicKeyToken =**  
  
     例如：  
  
     **设置 PublicKeyToken = 1234a5b6c1234567**  
  
3.  运行 CreateFullAndPartialMSI.bat。 此操作将创建两个应用程序 .msi 文件：CreateApplicationSample.msi 和 CreateApplicationSamplePartial.msi。  
  
4.  运行 CreateNewAppFromMSI.bat。 此操作将 CreateApplicationSample 应用程序导入到 BizTalk 组并将其安装在本地计算机上。  
  
5.  检查 C:\ScriptLog.txt 中的脚本日志文件，验证该脚本是否已记录其安装操作。  
  
6.  验证 CreateApplicationSample 应用程序是否显示在 BizTalk Server 管理控制台和“添加或删除程序”中。  
  
7.  运行 RemoveApp.bat。 此操作将从 BizTalk 管理数据库中删除 CreateApplicationSample，并从本地计算机中进行卸载。  
  
8.  检查 C:\ScriptLog.txt 中的脚本日志文件，验证该脚本是否已记录其卸载操作。 这些操作应显示在先前在安装期间记录的安装操作之后。  
  
9. 验证 CreateApplicationSample 应用程序是否不再显示在 BizTalk Server 管理控制台或“添加或删除程序”中。  
  
10. 验证是否已删除在安装期间创建的文件夹。  
  
11. 验证是否已从 GAC 卸载程序集。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹中）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)