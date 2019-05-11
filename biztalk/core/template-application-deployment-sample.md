---
title: 模板 （应用程序部署示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11933fe580b52ce63589c0906f0f9c17694b5c1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299478"
---
# <a name="template-application-deployment-sample"></a>模板 （应用程序部署示例）
本主题介绍如何使用应用程序部署的模板示例。  
  
 可以创建和使用两种类型的部署脚本自定义 BizTalk 应用程序部署： 预处理脚本和后处理脚本。 预处理脚本在应用程序安装和导入开始前以及卸载完成后调用。 后续处理脚本在应用程序安装和导入完成后以及在卸载开始前调用。  
  
 您可以编写预处理脚本和后续处理脚本，以便为每个这些操作调用它们。 或者，您可以将脚本后只有一个执行配置。 有关编写脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
 本主题演示如何编写和部署脚本，以便只有一个操作之前或之后调用它。 通过编写一个脚本来检查三个环境变量，以确定被调用的上下文中操作的值来执行此操作。 根据此上下文，该脚本将继续，或者停止执行。  
  
 本主题介绍如何执行以下步骤：  
  
1.  设置日志文件的位置，以便可以生成的脚本操作的日志文件。  
  
    > [!NOTE]
    >  最佳做法是，您始终应生成一个日志文件，以便可以验证脚本操作并解决任何问题。  
  
2.  创建新的 BizTalk 应用程序并向其添加示例脚本。  
  
3.  导出包含应用程序项目的.msi 文件。  
  
4.  从 BizTalk 组中删除应用程序，以便你可以.msi 文件导入回相同的组，以及从.msi 文件安装它。  
  
5.  导入应用程序，并检查日志文件以查看已记录导入操作。  
  
6.  安装该应用程序，并检查日志文件，请参阅安装日志已追加到日志文件。  
  
7.  查看日志文件，并记下脚本执行和执行时哪些操作。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 为此示例提供的两个.bat 文件包含导入、 安装和卸载的环境变量的值。 SamplePreProcessing.bat 包含预处理脚本的变量。 SamplePostProcessing.bat 包含后处理脚本的变量。 文件还演示了如何从脚本中记录消息。 可以将这些文件的相关部分复制到你的脚本。  
  
> [!IMPORTANT]
>  某些脚本文件中的注释不正确，如下所示：  
>   
>  在 SamplePreProcessing.bat 中，脚本注释"Pre uninstall part of the script called for an existing application"应"Post uninstall part of the script called for an existing application"  
>   
>  在 SamplePostProcessing.bat 中，脚本注释"Post uninstall part of the script called for an existing application"应阅读"Pre uninstall part of the script called for an existing application"  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 该示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹中的，按如下所示：  
  
 *\<示例路径\>* \Application Deployment\Template  
  
 如前文所述，该示例包括以下两个文件：  
  
-   SamplePreProcessing.bat  
  
-   SamplePostProcessing.bat  
  
## <a name="how-to-use-this-sample"></a>如何使用此示例  
 若要运行示例，请执行以下步骤。  
  
### <a name="to-set-the-logging-location"></a>若要设置日志记录位置  
  
-   打开这两个脚本示例并更改 LogFile 变量以指向要写入的日志文件的位置的位置。 必须提供包含文件名的完整路径。 如果它包含空格，必须将路径括在双引号 （"）。  
  
     例如：  
  
     set LogFile="*\<Samples Path\>* \ApplicationDeployment\Templates\SampleLogOut.txt"  
  
### <a name="to-create-a-new-application"></a>若要创建新的应用程序  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]和相应的 BizTalk 组。  
  
3. 右键单击**应用程序**，然后单击**新建**。  
  
4. 在中**应用程序名称**，类型`SamplesTemplate`，然后单击**确定**。  
  
### <a name="to-add-the-scripts-to-the-application"></a>若要将脚本添加到应用程序  
  
1.  展开刚创建的 SamplesTemplate 应用程序的文件夹，右击**资源**的左窗格中。  
  
2.  指向**外**然后单击**预处理脚本**。  
  
3.  单击**添加**并浏览至 SamplePreProcessing.bat。  
  
4.  选择该文件，然后单击**打开**。  
  
5.  在中**文件类型**，单击**system.biztalk: preprocessingscript**，然后单击**确定**。  
  
     SamplePreProcessing.bat 添加到应用程序，并显示在应用程序的资源文件夹中。  
  
6.  再次右键单击资源，指向**外**，然后单击**后续处理脚本**。  
  
7.  单击**添加**并浏览至 SamplePostProcessing.bat。  
  
8.  选择该文件，然后单击**打开**。  
  
9. 在中**文件类型**，单击**system.biztalk: postprocessingscript**，然后单击**确定**。  
  
     SamplePostProcessing.bat 添加到应用程序，并显示在应用程序的资源文件夹中。  
  
### <a name="to-export-an-msi-file"></a>若要导出的.msi 文件  
  
1.  在 BizTalk Server 管理控制台中，右键单击 SamplesTemplate 应用程序，指向**导出**，然后单击**MSI 文件**。  
  
2.  在欢迎使用导出向导页上，单击**下一步**。  
  
3.  在选择资源页上，单击**下一步**。  
  
4.  在指定 IIS 主机页上，单击**下一步**。  
  
5.  在依赖项页上，单击**下一步**。  
  
6.  在目标页上，在**目标应用程序名**，键入应用程序名称。  
  
7.  在中**MSI 文件以生成**，键入 MSI 文件的完整路径，然后单击**导出**。 例如：C:\MSI\SamplesTemplate.msi  
  
8.  在摘要页上单击**完成**。  
  
### <a name="delete-the-application"></a>删除应用程序  
  
-   在 BizTalk Server 管理控制台中，右键单击 SamplesTemplate 应用程序，然后依次**删除**。  
  
### <a name="to-import-the-msi-file"></a>若要导入.msi 文件  
  
1.  在 BizTalk Server 管理控制台中，右键单击**应用程序**，依次指向**导入**，然后单击**MSI 文件**。  
  
2.  在导入向导页中，欢迎在**MSI 文件导入**，键入之前导出，然后依次的.msi 文件的路径**下一步**。 如果有必要，则可以浏览 MSI 文件通过单击 **（...）** 按钮。  
  
3.  在应用程序设置页上，在**应用程序名称**下拉列表中，选择应用程序名称。  
  
4.  在中**可用的应用程序将引用添加到**，选择要添加的引用，如果有的话，应用程序，然后单击**下一步**。  
  
5.  在应用程序目标环境设置页上单击**下一步**。  
  
    > [!NOTE]
    >  不需要为本示例的目的指定的目标环境。 有关此功能的背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。 有关添加绑定文件的说明，请参阅[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)。  
  
6.  在导入摘要页面上，确认的摘要信息是否正确，然后依次**导入**。  
  
7.  在结果页上，单击**完成**。  
  
8.  打开时创建了脚本执行，并验证已记录导入操作的日志文件。  
  
### <a name="to-install-the-application"></a>若要安装该应用程序  
  
1.  双击.msi 文件并运行安装向导。  
  
2.  打开日志文件并验证安装操作已添加到日志记录信息。  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a>若要验证脚本运行是否正常  
  
-   打开日志文件并验证它们在指定的操作期间执行。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)