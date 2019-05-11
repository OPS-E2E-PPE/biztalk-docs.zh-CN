---
title: 自定义 Functoid （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d115e0a0594bc236487cca62c9b61355a8535116
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353405"
---
# <a name="custom-functoid-biztalk-server-sample"></a>自定义 Functoid （BizTalk Server 示例）
自定义 Functoid 示例演示如何为 BizTalk 映射器编写自定义 functoid。 您可以添加到 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。 当 BizTalk 映射器处于焦点时，将工具箱中显示该 functoid。  
  
 自定义 functoid 应位于 BizTalk 映射器程序集以识别它。 它可以在任何中进行编写。NET 兼容的语言，如C#或 Visual Basic。  
  
 此外，自定义 functoid 必须派生自`Microsoft.BizTalk.BaseFunctoids`类，并必须通过重写它们提供对某些方法的实现。 (`BaseFunctoid`随附的 Microsoft.BizTalk.BaseFunctoids.dll 程序集中定义类[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。)  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 自定义 Functoid 示例实现多个 functoid，每个派生自`BaseFunctoid`重写几个方法。  
  
 在实现自定义 functoid 时，可以公开其内联代码。 内联代码是为 functoid 执行计算。 BizTalk 映射器编译器从 functoid 提取内联代码，并将其嵌入编译的 XSLT 生成项目时。  
  
 如果自定义 functoid 没有公开任何内联代码，BizTalk 映射器生成 XSLT，调入程序集自定义 functoid 所在的位置。 在这种情况下，您必须确保您的自定义 functoid 程序集位于全局程序集缓存 (GAC) 以便 XSLT 引擎能够找到它。 自定义 functoid 还必须具有唯一的 GUID 属性。 BizTalk 映射器使用 GUID 来标识要加载的程序集。  
  
> [!IMPORTANT]
>  如果重复使用自定义 Functoid 示例代码，以实现自己的 functoid，您必须确保将 GUID 属性更改为其中一个是唯一的。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \XmlTools\CustomFunctoid  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|程序集信息C#的源代码。|  
|CBuildArray.bmp|工具箱位图。|  
|CConcat.bmp|工具箱位图。|  
|CExtractArray.bmp|工具箱位图。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们并同时删除 CustomFunctoid.dll。|  
|CLongestString.bmp|工具箱位图。|  
|CMultiply.bmp|工具箱位图。|  
|CustomFunctoid.cs|自定义 functoidC#的源代码。|  
|CustomFunctoid.csproj|自定义 functoidC#项目。|  
|CustomFunctoid.sln|自定义 functoid 解决方案。|  
|CustomFunctoidResources.resx|自定义 functoid 资源。|  
|Setup.bat|用于生成、 部署和启动示例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程生成并初始化自定义 Functoid 示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  
  
1.  在命令窗口中，将目录更改 (**cd**) 的以下文件夹：  
  
     \<*Samples Path*\>\XmlTools\CustomFunctoid  
  
2.  运行文件 Setup.bat，以执行以下操作：  
  
    -   生成示例项目。  
  
    -   将生成的程序集复制到 Developer Tools\Mapper Extensions 目录中。  
  
    -   将生成的程序集添加到 gac 中。  
  
        > [!NOTE]
        >  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行自定义 Functoid 示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具**菜单，然后选择**选择工具箱项**。  
  
2. 在中**选择工具箱项**对话框中，选择**BizTalk 映射器 Functoid**选项卡。  
  
3. 单击**重置**，然后单击**确定**。  
  
   > [!NOTE]
   >  如果自定义 functoid 没有公开任何内联代码，请确保它的程序集可在 GAC 中。  
  
4. 从**文件**菜单中，选择**退出**以关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
5. 启动**Visual Studio 命令提示符**。  
  
6. 在命令提示符处，键入**devenv /setup**。  
  
7. 启动**Microsoft Visual Studio**。  
  
    自定义 functoid （自定义 concatenate functoid、 最长字符串、 生成数组 functoid 和提取数组 functoid） 上显示**字符串 Functoid**工具箱和累计乘 functoid 的选项卡将显示在**累计 Functoid**选项卡。  
  
## <a name="removing-this-sample"></a>删除此示例  
 使用以下过程删除自定义 Functoid 示例。  
  
#### <a name="to-remove-this-sample"></a>若要删除此示例  
  
1. 删除从 functoid[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱。  
  
   > [!WARNING]
   >  如果运行 Cleanup.bat 后，仍显示过时的自定义 functoid （可能是由于内部缓存 Visual Studio） 工具箱中，请执行以下过程：  
  
   1. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具**菜单，然后选择**选择工具箱项**。  
  
   2. 在中**选择工具箱项**对话框中，选择**BizTalk 映射器 Functoid**选项卡。  
  
   3. 在列表中找到自定义 functoid （自定义将连接 functoid、 最长字符串、 生成数组 functoid、 提取数组 functoid 和累计乘号）。 单击各自**复选框**以删除 functoid，然后单击**确定**。  
  
      如果上述步骤不起作用，请按照以下过程。  
  
   4. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，单击**工具箱**时编辑映射以打开工具箱面板的选项卡。  
  
   5. 右键单击工具中，选择**选择项**。  
  
   6. 在选择项对话框中，单击**重置**，然后单击**确定**。  
  
   7. 关闭的所有实例[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
      如果上述步骤不起作用，请按照以下过程。  
  
   8. 启动**Visual Studio 命令提示符**以管理员身份。  
  
   9. 关闭所有正在运行的 Visual Studio 实例。  
  
   10. 发出以下命令：  
  
        `devenv /resetsettings`  
  
        `devenv /setup`  
  
   11. 从工具箱中，可以手动选择不需要的 functoid。 然后，右键单击该 functoid，然后单击**删除**。  
  
       如果上述步骤不起作用，请按照以下过程。  
  
   12. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目中，编辑映射以打开工具箱面板时单击工具箱选项卡。  
  
   13. 单击**累计 Functoid**组。  
  
   14. 右键单击你想要删除，然后选择的 functoid**删除**或按 delete 键。  
  
   15. 单击**字符串 Functoid**组。  
  
   16. 右键单击你想要删除，然后选择的 functoid**删除**或按 delete 键。  
  
2. 在命令窗口中，将目录更改 (**cd**) 的以下文件夹：  
  
    \<*Samples Path*\>\XmlTools\CustomFunctoid  
  
3. 运行文件 Cleanup.bat，执行以下操作：  
  
   -   从 Developer Tools\Mapper Extensions 目录中删除该程序集。  
  
   -   从 GAC 删除程序集。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a>请参阅  
 [使用 BaseFunctoid](../core/using-basefunctoid.md)   
 [XML 工具（BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)