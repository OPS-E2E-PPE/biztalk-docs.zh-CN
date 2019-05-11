---
title: 扩展映射器 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, examples
- XML tools
- BizTalk Mapper, extending
- examples, BizTalk Mapper
- examples, XML tools
ms.assetid: 6010a13f-b715-4766-ad91-5aa9b98589e3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08a926a0adffe20a8c3b5da14dd9dbd042101558
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345897"
---
# <a name="extending-mapper-biztalk-server-sample"></a>扩展映射器 （BizTalk Server 示例）
扩展映射器示例演示如何使用和扩展 BizTalk 映射器。 示例包含多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映射文件 （.btm 文件），其中每个阐释了 BizTalk 映射器的功能。  

## <a name="what-this-sample-does"></a>本示例的用途  
 扩展映射器示例使用基于内容的路由 (CBR)，并不使用业务流程。 通过指定此示例中的筛选器发送端口，它直接连接到示例接收端口。 映射是在要将应用于已处理文档的发送端口上指定的。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \XmlTools\ExtendingMapper  

 下表显示了本示例中的文件及其用途说明：  


|                                                                             文件                                                                             |                                                         Description                                                          |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| MapperClassLibrary\AssemblyInfo.cs, MapperClassLibrary\MapperClassLibrary.csproj, MapperClassLibrary\MapperHelper.cs, MapperClassLibrary\MapperClassLibrary.sln | Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]® 项目文件和 Visual C#® 源文件。 |
|                                                                           Cleanup.bat                                                                           |                      用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。                       |
|                                                                         Destination.xsd                                                                         |                                                         架构文件。                                                         |
|                                                           ExtendingMapper.btproj, ExtendingMapper.sln                                                           |                                     此示例的 BizTalk 项目和解决方案文件。                                      |
|                                                                       ExtendingMapper.xml                                                                       |                                                         源 XML。                                                          |
|                                                                   ExtendingMapperBinding.xml                                                                    |                                                         绑定 XML。                                                         |
|                                                                      ExternalAssembly.xml                                                                       |                                                    外部程序集 XML。                                                    |
|                                                                      OverridingMapXslt.btm                                                                      |                                                          映射文件。                                                           |
|                                                                      OverridingMapXslt.xml                                                                      |                                                     替代映射 XML。                                                      |
|                                                                     OverridingMapXslt.xslt                                                                      |                                                 替代映射样式表。                                                  |
|                                                                Scriptor_CallExternalAssembly.btm                                                                |                                                       示例映射文件。                                                       |
|                                                            Scriptor_GlobalVariableInInlineScript.btm                                                            |                                                       示例映射文件。                                                       |
|                                                                   Scriptor_InlineScripts.btm                                                                    |                                                       示例映射文件。                                                       |
|                                                                     Scriptor_InlineXslt.btm                                                                     |                                                       示例映射文件。                                                       |
|                                                         Scriptor_InlineXsltCallingExternalAssembly.btm                                                          |                                                       示例映射文件。                                                       |
|                                                                  Scriptor_XsltCalltemplate.btm                                                                  |                                                       示例映射文件。                                                       |
|                                                                            Setup.bat                                                                            |                                           用于生成并初始化示例。                                           |
|                                                                           Source.xsd                                                                            |                                                         架构文件。                                                         |

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程生成并初始化扩展映射器示例。  

#### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  

1. 在命令窗口中，将目录更改 (**cd**) 的以下文件夹：  

    *\<Samples Path\>* \XmlTools\ExtendingMapper  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 创建输入 (\In) 和为本示例的输出 (\Out) 文件夹。  

   - 编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  

     如果你想要使用 Scriptor_CallExternalAssembly.btm 或 Scriptor_InlineXsltCallingExternalAssembly.btm 映射，在 Visual Studio 中打开 ExtendingMapper.sln 并进行以下修改 （否则为转到步骤 3）：  

   1. 在解决方案资源管理器，打开 Scriptor_CallExternalAssembly.btm。  

   2. 映射器网格中，选择脚本 functoid。  

   3. 在属性网格中，选择**脚本**属性，并单击省略号 （...） 按钮以配置 functoid 脚本。  

   4. 在中**配置脚本 Functoid**对话框中，选择**脚本 Functoid 配置**，并指定以下内容：  


      |      将此项设置       |                           与此                            |
      |---------------------|--------------------------------------------------------------|
      |   **脚本类型**   |                      外部程序集                       |
      | **脚本程序集** | Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary |
      |  **脚本类**   |    Microsoft.Samples.BizTalk.ExtendingMapper.MapperHelper    |
      |  **脚本方法**  |                           MyConcat                           |


   5. 从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**文件**菜单中，选择**保存**若要将更改保存到映射文件，然后关闭解决方案。  

3. 按任意键继续 Setup.bat。  

   > [!IMPORTANT]
   >  如果你想要使用 Scriptor_InlineXsltCallingExternalAssembly.btm，则必须编辑 ExternalAssembly.xml 文件。 BizTalk 使用 ExternalAssembly.xml 将映射器扩展对象已注册命名空间映射到.NET 程序集。 由于依赖程序集引用了其完全限定名 （包括其公钥标记，将自动生成），则必须更新此值。 如果您不想要使用 Scriptor_InlineXsltCallingExternalAssembly.btm，不需要完成步骤 a 到 e。  

4. 在 Windows 资源管理器，导航到\<Windows 文件夹\>\assembly\\。  

   1. 右键单击**Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary** ，然后选择**属性**。  

   2. 复制公钥标记值。  

   3. 在文本编辑器中，打开*\<示例路径\>* \XML Tools\ExtendingMapper\ExternalAssembly.xml。  

   4. 选择<strong>AssemblyName="Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary，版本 = 1.0.0.0，区域性 = 中性，PublicKeyToken = 68496d20c737d84b"</strong>属性，并替换**PublicKeyToken**公钥标记值的值中复制步骤 c。  

   5. 保存并关闭 ExternalAssembly.xml。  

   > [!NOTE]
   >  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  

#### <a name="to-configure-enlist-and-start-the-send-port"></a>若要配置、 登记并启动发送端口  

1. 单击**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。  

2. 在 BizTalk Server 管理控制台中，单击以展开**BizTalk Server 管理**，单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，并单击以展开**应用程序**。  

3. 单击此项可展开**ExtendingMapperApplication**，然后单击**发送端口**。  

4. 在右窗格中，右键单击**发送端口**，然后单击**属性**。  

5. 在中**ExtendingMapperSP – 发送端口属性**对话框中，单击**出站映射**页。  

    在中**地图**列中，从下拉列表中，选择所需的映射，然后单击**确定**。 下表所述的映射。  


   |                                 要应用属性的映射                                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
   |---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_CallExternalAssembly        |                                                                                                                                                                                                                                                                                                                                       演示如何调用外部.NET 程序集从中的函数**脚本**functoid 在映射中，基于此 functoid 的输入参数。 这有助于完全隔离任何处理逻辑与映射文件。 此映射文件与本示例使用附带的 MapperClassLibrary.dll 程序集。                                                                                                                                                                                                                                                                                                                                       |
   |           Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineScripts           |                                                                                                                                                                                                                                                                                                                                                                                                                 演示如何编写简单的内联脚本内**脚本**functoid 使用.NET 语言如 C#、 Visual Basic.NET 和 JScript.NET 的映射文件中。                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |   Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_GlobalVariableInInlineScript    |                                                                                                                                                                                                                                                                                                                                                                                        演示如何在的内联脚本中使用全局变量**脚本**functoid。 全局变量通常用于维护跨不同的映射文件中的状态信息**脚本**functoid。                                                                                                                                                                                                                                                                                                                                                                                         |
   |            Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineXslt             |                                                                                                                                                                                                                                                                                                                                   演示如何构造使用原始内联 XSLT 在目标文档中的结构内**脚本**映射中的 functoid。 您可以构造目标文档中使用的某些部分**脚本**具有内联 XSLT 时不能为此，在 BizTalk 映射器中使用其他 functoid 的 functoid。                                                                                                                                                                                                                                                                                                                                   |
   |         Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_XsltCalltemplate          |                                                                                                                                                                                                                                演示如何使用 XSLT 调用模板内的目标文档中创建结构**脚本**映射中的 functoid。 XSLT 是调用模板可以接受参数，因此您可以创建结构的内联 XSLT 调用模板的优于基于输入参数**脚本**functoid。 您可以构造目标文档中使用的某些部分**脚本**具有内联 XSLT 时不能为此，在 BizTalk 映射器中使用其他 functoid 的 functoid。                                                                                                                                                                                                                                 |
   | Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineXsltCallingExternalAssembly |                                                                                                                                                                                                                           演示如何调用外部.NET 程序集从的内联 XSLT 内的**脚本**functoid 在映射中的。 介绍了如何覆盖**自定义扩展 XML**与自定义扩展插件文件包含要调用的外部.NET 程序集的详细信息的 externalassembly_extxml.xml 取代 BizTalk 映射器网格的属性。 您可以构造目标文档中使用的某些部分**脚本**具有内联 XSLT 时不能执行该操作使用其他 functoid 在映射器 UI 中的 functoid。                                                                                                                                                                                                                           |
   |             Microsoft.Samples.BizTalk.ExtendingMapper. OverridingMapXslt              | 演示如何使用自定义 XSLT 文件的 BizTalk 映射器文件的已编译的 XSLT 来完全覆盖。 您可以执行此操作通过重写**自定义 XSL 路径**属性和可选**自定义扩展 XML** BizTalk 映射器网格的属性。 你提供的自定义 XSLT 文件是包含在编译[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要在运行时使用的项目的程序集。 在这种情况下，将忽略映射文件 (.btm) 的内容。 此映射文件使用 OverridingMapXslt.xslt 和 OverridingMapXslt.xml**自定义 XSL 路径**并**自定义扩展 XML**属性，分别。<br /><br /> 您可以验证在解决方案资源管理器中的映射文件。 然后可以为您可以编辑和使用的模板文件将其**自定义 XSL 路径**BizTalk 映射器网格的属性。 它不是可以生成使用 BizTalk 映射器 XSLT 时，可以使用此选项。 |

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行扩展映射器示例。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  复制到输入文件夹中，输入文件 ExtendingMapper.xml *\<示例路径\>* \XmlTools\ExtendingMapper\In。  

2.  请注意，该文件将转换并路由到如何*\<示例路径\>* \XmlTools\ExtendingMapper\Out 文件夹。 发生的转换取决于应用的映射确定。  

## <a name="see-also"></a>请参阅  
 [XML 工具（BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)