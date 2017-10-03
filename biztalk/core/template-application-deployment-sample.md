---
title: "模板 （应用程序部署示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f32e9432800249e6cbc64d36e281fb564648f78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="template-application-deployment-sample"></a>模板（应用程序部署示例）
本主题介绍如何使用“模板”示例来进行应用程序部署。  
  
 你可以创建和部署脚本的两种用于自定义 BizTalk 应用程序部署： 预先处理脚本和脚本的后续处理。 预处理脚本在应用程序安装和导入开始前以及在卸载完成后调用。 后续处理脚本在应用程序安装和导入完成后以及在卸载开始前调用。  
  
 您可以编写预处理脚本和后续处理脚本，以便针对上述每项操作进行调用。 或者，您也可以将脚本配置为仅在其中一项操作后执行。 有关编写脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
 本主题演示如何编写并部署脚本，使其仅在一项操作之前或之后调用。 具体方法是：编写一段脚本，此脚本通过检查三个环境变量的值来决定操作调用上下文中的操作。 根据此上下文，脚本将继续执行或停止执行。  
  
 本主题介绍如何执行以下步骤：  
  
1.  设置日志文件位置，以便生成脚本操作的日志文件。  
  
    > [!NOTE]
    >  最佳做法是，始终生成日志文件以便验证脚本操作并解决任何问题。  
  
2.  新建一个 BizTalk 应用程序，并向该应用程序添加示例脚本。  
  
3.  导出包含应用程序项目的 .msi 文件。  
  
4.  从 BizTalk 组删除此应用程序，以便将此 .msi 文件导入回原来的组中，并从此 .msi 文件进行安装。  
  
5.  导入此应用程序，然后检查日志文件以查看是否已记录导入操作。  
  
6.  安装此应用程序，然后检查日志文件以查看是否已将安装日志附加到该日志文件中。  
  
7.  查看日志文件，注意脚本执行了哪些操作以及执行这些操作的时间。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 针对本示例提供的两个 .bat 文件包含用于导入、安装和卸载的环境变量的值。 SamplePreProcessing.bat 包含预处理脚本的变量。 SamplePostProcessing.bat 包含后处理脚本的变量。 这些文件还演示了如何记录来自脚本的消息。 您可以将这些文件的相关部分复制到脚本中。  
  
> [!IMPORTANT]
>  脚本文件中的某些注释不正确，具体如下：  
>   
>  在 SamplePreProcessing.bat 中，脚本注释“Pre uninstall part of the script called for an existing application”应为“Post uninstall part of the script called for an existing application”。  
>   
>  在 SamplePostProcessing.bat 中，脚本注释“Post uninstall part of the script called for an existing application”应为“Pre uninstall part of the script called for an existing application”。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹，，如下所示：  
  
 *\<示例路径 >*\Application Deployment\Template  
  
 如前所述，本示例包括下列两个文件：  
  
-   SamplePreProcessing.bat  
  
-   SamplePostProcessing.bat  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 若要运行本示例，请执行下列步骤。  
  
### <a name="to-set-the-logging-location"></a>设置日志记录位置  
  
-   打开这两个脚本示例并更改 LogFile 变量，使其指向日志文件的写入位置。 您必须提供包含文件名的完整路径。 如果该路径包含空格，则必须将该路径括在双引号 (") 中。  
  
     例如：  
  
     设置日志文件 ="*\<示例路径 >*\ApplicationDeployment\Templates\SampleLogOut.txt"  
  
### <a name="to-create-a-new-application"></a>新建应用程序  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] 和 BizTalk 组。  
  
3.  右键单击**应用程序**，然后单击**新建**。  
  
4.  在**应用程序名称**，类型`SamplesTemplate`，然后单击**确定**。  
  
### <a name="to-add-the-scripts-to-the-application"></a>若要将脚本添加到应用程序  
  
1.  展开你刚创建 SamplesTemplate 应用程序的文件夹，右击**资源**的左窗格中。  
  
2.  指向**添加**单击**预处理脚本**。  
  
3.  单击**添加**并浏览到 SamplePreProcessing.bat。  
  
4.  选择该文件，然后单击**打开**。  
  
5.  在**文件类型**，单击**System.BizTalk:PreprocessingScript**，然后单击**确定**。  
  
     SamplePreProcessing.bat 将添加到应用程序中，并且显示在应用程序的“资源”文件夹中。  
  
6.  再次右键单击资源，指向**添加**，然后单击**后处理脚本**。  
  
7.  单击**添加**并浏览到 SamplePostProcessing.bat。  
  
8.  选择该文件，然后单击**打开**。  
  
9. 在**文件类型**，单击**System.BizTalk:PostprocessingScript**，然后单击**确定**。  
  
     SamplePostProcessing.bat 将添加到应用程序中，并且显示在应用程序的“资源”文件夹中。  
  
### <a name="to-export-an-msi-file"></a>导出 .msi 文件  
  
1.  在 BizTalk Server 管理控制台中，右键单击 SamplesTemplate 应用程序，指向**导出**，然后单击**MSI 文件**。  
  
2.  在欢迎使用导出向导页上，单击**下一步**。  
  
3.  在选择资源页上，单击**下一步**。  
  
4.  在指定的 IIS 主机页上，单击**下一步**。  
  
5.  在依赖关系页上，单击**下一步**。  
  
6.  在目标页上，在**目标应用程序名称**，键入应用程序名称。  
  
7.  在**MSI 文件以生成**，键入 MSI 文件的完整路径，然后单击**导出**。 示例： C:\MSI\SamplesTemplate.msi  
  
8.  在摘要页上单击**完成**。  
  
### <a name="delete-the-application"></a>删除应用程序。  
  
-   在 BizTalk Server 管理控制台中，右键单击 SamplesTemplate 应用程序，并依次**删除**。  
  
### <a name="to-import-the-msi-file"></a>导入 .msi 文件  
  
1.  在 BizTalk Server 管理控制台中，右键单击**应用程序**，指向**导入**，然后单击**MSI 文件**。  
  
2.  在导入向导页上，欢迎在**MSI 文件以导入**，键入您之前已导出，，然后单击的.msi 文件的路径**下一步**。 如果有必要，则可以浏览的 MSI 文件通过单击**（…）**按钮。  
  
3.  在应用程序设置页上，在**应用程序名称**下拉列表中，选择应用程序名称。  
  
4.  在**可用的应用程序将引用添加到**，选择要向其中添加引用，如果有的话，应用程序，然后单击**下一步**。  
  
5.  在应用程序目标环境设置页上，单击**下一步**。  
  
    > [!NOTE]
    >  在本示例中，您无需指定目标环境。 有关此功能的背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。 有关添加绑定文件的说明，请参阅[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)。  
  
6.  在导入摘要页面上，确认验证摘要信息是否正确，并依次**导入**。  
  
7.  在结果页上，单击**完成**。  
  
8.  打开执行脚本时创建的日志文件，并验证是否已记录导入操作。  
  
### <a name="to-install-the-application"></a>若要安装应用程序  
  
1.  双击 .msi 文件并运行安装向导。  
  
2.  打开日志文件，并验证是否已将安装操作添加到日志纪录信息中。  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a>验证脚本运行是否正常  
  
-   打开日志文件，验证脚本在指定操作期间是否执行。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹中）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)