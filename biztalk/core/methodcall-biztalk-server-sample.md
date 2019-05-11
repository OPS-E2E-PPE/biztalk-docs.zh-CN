---
title: MethodCall （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 78e190920695ebfb1f5654dcb4abcf95beab085f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394483"
---
# <a name="methodcall-biztalk-server-sample"></a>MethodCall （BizTalk Server 示例）
MethodCall 示例演示如何调用。从 BizTalk Server 业务流程的基于网络的方法。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例与交互。使用以下步骤序列的基于网络的方法：  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程从 In 文件夹检索 XML 输入的文件。 此文件包含有关加法或减法你想要执行的数学库。  

2. 业务流程将调用包含的数学库执行的加法或减法 XML 输入文件中指定。  

3. 相应的数学库方法，要么**外**或**Subtract**，执行所请求的计算，并将结果打包为一个 XML 文档。  

4. 业务流程将生成的.xml 文件放在 Out 文件夹中。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 此示例演示以下功能：  

-   利用在业务流程中的已升级的属性。 InputSchema.xsd 中的三个元素是作为可分辨字段升级。 当业务流程接收到输入的消息时，它获取这三个字段的值，并将其分配给对应业务流程中声明的变量。  

-   使用**判定**形状表示业务流程中的"-if-then-else"逻辑。 业务流程将可分辨字段的值分配给内部变量后，会进入**判定**形状中，以检查是否应执行加法还是减法。 如果不需要执行任何操作，业务流程将终止。  

-   从业务流程调用外部程序集。 如果要执行加法，业务流程调用外部 C# 程序集，并传入两个参数，以执行加法。 相同的过程适用于减法。  

    > [!NOTE]
    >  您需要将程序集安装到全局程序集缓存中才能调用从业务流程;否则将在运行时期间收到 XLANG 错误。  

-   使用**消息赋值**形状以构造输出消息。  

-   通过将以下代码放在表达式形状中调试业务流程：  

    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  

     通过使用，还可以编写将结果记录到事件日志：  

    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*Samples Path*\>\Orchestrations\MethodCall\  

 下表显示了本示例中的文件及其用途说明：  


|                                          文件                                           |                                                                                           Description                                                                                            |
|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        Cleanup.bat                                         | 用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。 |
|                                         Input.xml                                          |                                                                                        示例输入的文件。                                                                                        |
|                                         Setup.bat                                          |                                                                            用于生成和初始化本示例。                                                                             |
| 在 \MathLibrary 文件夹中：<br /><br /> AssemblyInfo.cs、 MathHelper.cs 和 MathLibrary.csproj |                                                                此示例使用数学库的项目和源代码文件。                                                                |
|       在 \MethodCallSample 文件夹中：<br /><br /> InputSchema.xsd、 OutputSchema.xsd       |                                                                    架构的输入和输出.xml 文件，分别。                                                                    |
| 在 \MethodCallSample 文件夹中：<br /><br /> MethodCallSample.btproj、 MethodCallSample.sln |                                                                           本示例的项目和解决方案文件。                                                                            |
|          在 \MethodCallSample 文件夹中：<br /><br /> MethodCallSampleBinding.xml          |                                                                          用于如端口绑定之类的自动化设置。                                                                          |
|             在 \MethodCallSample 文件夹中：<br /><br /> MethodCallService.odx             |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 调用数学库以执行所请求的计算的业务流程。                |

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

#### <a name="to-build-and-initialize-the-methodcall-sample"></a>若要生成并初始化 MethodCall 示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*Samples Path*\>\Orchestrations\MethodCall  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 创建输入 (In) 和输出 (Out) 文件夹中，为此示例在 MethodCall 文件夹。  

   - 编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收到业务流程的端口。  

   - 启用该接收位置，并启动发送端口。 登记并启动业务流程。  

> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  

## <a name="running-this-sample"></a>运行本示例  

#### <a name="to-run-the-methodcall-sample"></a>若要运行 MethodCall 示例  

1.  将文件 Input.xml 的副本粘贴到 In 文件夹。  

2.  查看在 Out 文件夹中创建的.xml 文件。 此文件包含所请求的加法或减法计算的结果。 此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.  

3.  你可以修改输入的文件以请求不同的加法或减法计算。  

## <a name="uninstalling-this-sample"></a>卸载本示例  

#### <a name="to-uninstall-the-methodcall-sample"></a>若要卸载 MethodCall 示例  

1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改 (**cd**) 对\<*示例路径*\>\Orchestrations\MethodCall\\。  

2. 运行 Cleanup.bat。  

## <a name="see-also"></a>请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)