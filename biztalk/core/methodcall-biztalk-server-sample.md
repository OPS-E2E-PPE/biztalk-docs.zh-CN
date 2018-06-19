---
title: MethodCall （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, calling
- examples, orchestrations
- orchestrations, methods
ms.assetid: 6bdc72da-9478-403a-b706-3089b7374ac7
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16b97b7c81b36774bcf2eaff53a1a4ff91b6f9e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973971"
---
# <a name="methodcall-biztalk-server-sample"></a>MethodCall （BizTalk Server 示例）
MethodCall 示例演示如何从 BizTalk Server 业务流程调用基于 .NET 的方法。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例通过下列步骤与基于 .NET 的方法交互：  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程从 In 文件夹中检索 XML 输入文件。 此文件包含想要数学库执行的加法或减法的信息。  
  
2.  业务流程调用所包含的数学库来执行 XML 输入文件中指定的加法或减法。  
  
3.  适当的数学库方法，或者**添加**或**Subtract**、 执行所请求的计算和包作为 XML 文档的结果。  
  
4.  业务流程将结果 .xml 文件放入 Out 文件夹中。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 本示例演示以下功能：  
  
-   在业务流程中利用已升级的属性。 InputSchema.xsd 中的三个元素已升级为可分辨字段。 业务流程接收到输入消息时，会获得这三个字段的值并将它们分配给在业务流程中声明了的相应变量。  
  
-   使用**确定**形状来表示业务流程中的"-if-then-else"逻辑。 业务流程将可分辨的字段的值分配给内部变量后，进入**确定**形状以检查是否应执行加法或减法。 如果不需要执行任何操作，业务流程将终止。  
  
-   从业务流程调用外部程序集。 如果要执行加法，业务流程将调用外部 C# 程序集并传入两个参数以执行加法。 该过程同样适用于减法。  
  
    > [!NOTE]
    >  您需要将程序集安装到全局程序集缓存中，然后才能从业务流程调用它，否则运行期间将收到 XLANG 错误。  
  
-   使用**消息分配**形状构造输出消息。  
  
-   通过将以下代码放入表达式形状来调试业务流程：  
  
    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  
  
     您也可以使用如下代码将结果写入事件日志中：  
  
    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Orchestrations\MethodCall\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Input.xml|示例输入文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \MathLibrary 文件夹中：<br /><br /> AssemblyInfo.cs、MathHelper.cs 和 MathLibrary.csproj|本示例使用的数学库的项目文件和源文件。|  
|在 \MethodCallSample 文件夹中：<br /><br /> InputSchema.xsd、OutputSchema.xsd|分别为输入和输出 .xml 文件的架构。|  
|在 \MethodCallSample 文件夹中：<br /><br /> MethodCallSample.btproj、MethodCallSample.sln|本示例的项目文件和解决方案文件。|  
|在 \MethodCallSample 文件夹中：<br /><br /> MethodCallSampleBinding.xml|用于如端口绑定之类的自动化设置。|  
|在 \MethodCallSample 文件夹中：<br /><br /> MethodCallService.odx|调用数学库以执行所请求的计算的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-methodcall-sample"></a>生成并初始化 MethodCall 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Orchestrations\MethodCall  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在 MethodCall 文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹。  
  
    -   编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。  
  
    -   创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口，并将它们绑定到业务流程。  
  
    -   启用接收位置并启动发送端口。 登记，并启动业务流程。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-methodcall-sample"></a>运行 MethodCall 示例  
  
1.  将文件 Input.xml 的副本粘贴到 In 文件夹。  
  
2.  查看在 Out 文件夹中创建的 .xml 文件。 此文件包含请求的加法或减法的计算结果。 此文件的名称的格式是\< *MessageID*\>.xml，其中 *\<MessageID\>*  GUID 生成以唯一标识消息.  
  
3.  您可以修改输入文件以请求不同的加法或减法计算。  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-methodcall-sample"></a>卸载 MethodCall 示例  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 到\<*示例路径*\>\Orchestrations\MethodCall\\。  
  
2.  运行 Cleanup.bat。  
  
## <a name="see-also"></a>另请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)