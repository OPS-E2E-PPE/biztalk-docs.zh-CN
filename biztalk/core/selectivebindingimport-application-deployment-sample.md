---
title: SelectiveBindingImport （应用程序部署示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding files, importing
- examples, applications
- binding files, examples
- examples, importing
- applications, binding files
- applications, examples
- applications, importing
- deploying, scripts
- examples, binding files
ms.assetid: 963bfc80-8cc4-4d90-96b4-e85ae04405cf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ebd27317b549e773fd9c1a1f5c8e24a4c1f0d12
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254485"
---
# <a name="selectivebindingimport-application-deployment-sample"></a>SelectiveBindingImport （应用程序部署示例）
本主题说明如何使用 SelectiveBindingImport 示例。 此示例脚本可用于应用程序导入不同的目标环境时，向应用程序将不同的绑定。 当你想要将绑定导入从绑定的网络共享存储的文件时，可以使用此方法。  
  
> [!NOTE]
>  如果不需要自动导入绑定文件从网络共享应用程序导入过程中，您可以将其添加到了不同目标环境指定的应用程序不同的绑定文件。 导入应用程序时，可以指定的环境，并将自动应用该环境的绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
 通常，BizTalk 应用程序被移动从开发到测试到过渡环境，然后对生产环境。 在不同环境中使用的绑定是通常不同的。 此示例，你可以使用应用不同的环境的绑定，如下所示：  
  
1.  将你想要使用的网络共享上的所有绑定文件。  
  
2.  将后续处理脚本添加到将从位置导入此特定目标环境的正确的绑定文件应用程序导入过程中的应用程序。 该脚本通过读取环境变量名为的 %ENVIRONMENT%的设置在本地计算机上检测环境。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何有选择地导入绑定文件从网络共享通过使用 BizTalk 应用程序.msi 文件中包含一个后处理脚本。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 以下示例文件夹和文件下的可以找到 *\<示例路径\>* \Application Deployment\SelectiveBindingImport:  
  
-   Develop （文件夹）  
  
    -   Dev.xml  
  
-   Production （文件夹）  
  
    -   Production.xml  
  
-   Staging （文件夹）  
  
    -   Staging.xml  
  
-   Test （文件夹）  
  
    -   Test.xml  
  
-   SelectiveBindings.bat  
  
## <a name="how-to-use-this-sample"></a>如何使用此示例  
 使用以下过程才能运行此示例。  
  
### <a name="to-run-the-sample"></a>若要运行示例  
  
1. 运行**从 Build.Bat *\<示例路径\>* deployment\createapp**目录。 这将创建以下文件中的 *\<示例路径\>* \Application Deployment\CreateApp\Dlls 文件夹：Schemas.dll、 Maps.dll 和 Orchestrations.dll。  
  
2. **创建应用程序。** 在 BizTalk Server 管理控制台中，创建应用程序，如中所述[如何创建应用程序](../core/how-to-create-an-application.md)。  
  
3. **将添加到应用程序第一步中创建的.dll 文件。** 有关说明，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
4. **创建环境变量，如下所示：**  
  
   1.  在开始菜单中，右键单击**我的电脑**然后单击**属性**。  
  
   2.  上**高级**选项卡上，单击**环境变量**。  
  
   3.  在中**用户变量**部分中，单击**新建**。  
  
   4.  在中**变量名**，类型**环境**。  
  
   5.  在中**变量值**，类型上的环境的以下值：**开发**，**生产**，**过渡**，或**测试**。 这些值是区分大小写。  
  
5. 单击**确定**三次。  
  
6. **将绑定文件复制到文件系统上的位置。** 将.xml 绑定文件从开发、 测试、 过渡和生产文件夹复制到文件系统上的位置。  
  
7. **编辑后续处理脚本。** 编辑 SelectiveBindings.bat，如下所示：  
  
   1.  **指定绑定文件的位置。** 在包含 BINDINGS_LOC 的行，删除 REM，然后提供复制绑定文件的位置的路径。  
  
        例如：  
  
        BINDINGS_LOC=C:\MyBindings  
  
   2.  **指定应用程序名称。** 在包含 APPLICATION_NAME 的行，删除 REM，然后提供你想要将绑定导入到其中的应用程序的名称。  
  
        例如：  
  
        APPLICATION_Name=SelectiveBindingImport  
  
8. **将脚本添加到应用程序作为后续处理脚本。** 有关说明，请参阅[How to Add 的预处理或后处理脚本保存到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。  
  
9. **导出应用程序。** 有关说明，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
10. **删除应用程序。** 有关说明，请参阅[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。  
  
11. **导入应用程序。** 有关说明，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 不需要指定目标环境。  
  
12. **验证已应用正确的绑定文件。** 可以通过检查接收位置的说明字段，如下所示执行此操作：  
  
    1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
    2. 在控制台树中，展开 BizTalk 组、 BizTalk 应用程序和接收位置文件夹。  
  
    3. 在右窗格中，查看接收位置的说明。  
  
13. **安装应用程序。** 有关说明，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md)   
 [部署 BizTalk 应用程序](../core/deploying-biztalk-applications.md)