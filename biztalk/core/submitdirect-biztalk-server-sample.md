---
title: SubmitDirect （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- receive adapters, examples
- examples, receive adapters
ms.assetid: 3540368b-cf46-4c83-a87b-94aec9cd1b36
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dce1313fd851d04a490a31b602611072ade2242d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396057"
---
# <a name="submitdirect-biztalk-server-sample"></a>SubmitDirect （BizTalk Server 示例）
SubmitDirect 示例演示如何以编程方式提交单向和请求/响应消息，向 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从。基于 NET 的应用程序。 此示例演示如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Api，可用于适配器。 它还提供了一个接收适配器，名为 Submit 的可用于将消息提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="prerequisites"></a>先决条件  
 运行此示例之前，请确保为属于 BizTalk Isolated Host Users 组的用户身份登录。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何执行与 BizTalk 适配器相关的各种任务。 具体而言，它显示如何：  

- 使用外部运行的独立适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程。 Submit 适配器是一个独立的适配器，因为外部创建的进程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]（您启动它与.NET 应用程序） 的过程。  

- 提交到消息批[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 Submit 适配器使用批消息提交功能同时提交多条消息。  

- 将消息以同步方式使用请求/响应范例，以及使用单向范例异步提交。  

- 注册适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此示例演示了如何注册适配器，并提供注册可执行文件，可自动注册适配器。  

  此示例实际上有两个示例中，如下所示：  

- **单向消息批的提交。** 控制台应用程序 SubmitMessages.exe 获取从其命令行字符串并将作为单独的消息为每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 每个提交的接收位置处拾取消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 通过直通接收和发送管道发送，然后写入到文本文件。  

- **提交请求/响应消息。** 控制台应用程序 SubmitRequest.exe 获取在其命令行上指定的.xml 文件，并将其提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此.xml 文件的架构定义包含两个整数字段的元素。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提取的.xml 文件，并与业务流程 （使用一个请求/响应端口） 对其进行处理。 它使用映射来生成 XML 响应消息返回一个整数，是在请求中的两个整数的乘积。 当控制台应用程序收到响应时，它将显示结果。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\  

 下表列出了在此示例中的文件，并描述其用途。  


|                                                                                                                     文件                                                                                                                      |                                                                                              Description                                                                                               |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                   Cleanup.bat                                                                                                                    |    取消部署程序集，并将其从全局程序集缓存 (GAC) 中;删除发送和接收端口;根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。    |
|                                                                                                                    Setup.bat                                                                                                                     |                                                                                  生成并初始化本示例。                                                                                   |
|                                                                                                                 SubmitDirect.sln                                                                                                                 |                                包括 ProcessRequest 文件夹和其他文件夹中的 Microsoft Visual C# 项目中的 BizTalk 项目的解决方案文件。                                 |
|                                                                                               SubmitMessagesBinding.xml, SubmitRequestBinding.xml                                                                                                |                                                                             用于如端口绑定之类的自动化设置。                                                                             |
|                                                              \ProcessRequest 文件夹的位置：<br /><br /> DocIn.xsd、 DocOut.xsd、 Multiplier.odx、 Multiply.btm、 ProcessRequest.btproj                                                               |                                               提供了在请求/响应方案中执行整数乘法的 BizTalk 项目。                                                |
|                                                                       \SubmitMessages 文件夹的位置：<br /><br /> AssemblyInfo.cs、 SubmitMessages.cs、 SubmitMessages.csproj                                                                       |                                提供了用于将其命令行字符串参数传递作为单独的消息的批处理的控制台应用程序的 Visual C# 项目。                                |
|                                                                \SubmitRequest 文件夹的位置：<br /><br /> AssemblyInfo.cs、 DocInstance.xml、 SubmitRequest.cs、 SubmitRequest.csproj                                                                |                                 传递一个包含两个整数相乘的.xml 文件 (DocInstance.xml) 的控制台应用程序提供了一个 C# 项目。                                 |
| 在 \TransportProxyUtils 文件夹中：<br /><br /> AssemblyInfo.cs、 MessageHelper.cs、 MessagingAPIInterface.cs、 MessagingAPIs.cs、 ResponseCallBack.cs、 TpBatchAsyncCallback.cs、 TpBatchAsyncResult.cs、 TpBatchStatus.cs、 TransportProxyUtils.csproj | 提供了用于实现方法的同步和异步消息提交和用于批处理和单个请求消息提交 Submit 适配器的运行时部分的 C# 项目。 |
|                                                              在 \TransportProxyUtilsReg 文件夹中：<br /><br /> AssemblyInfo.cs、 RegisterAdapter.cs，TransportProxyUtilsReg.csproj                                                               |           提供了一个演示了可用于注册适配器使用的代码的 Visual C# 项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。           |
|                                                           在 \TransportProxyUtilsUI 文件夹中：<br /><br /> AssemblyInfo.cs、 TransportProxyUtilsMgmt.cs，TransportProxyUtilsUI.csproj                                                            |                                                           提供了用于 Submit 适配器的用户界面部分的 Visual C# 项目。                                                           |

## <a name="building-and-initializing-the-sample"></a>生成并初始化示例  

#### <a name="to-build-and-initialize-the-submitdirect-sample"></a>若要生成并初始化 SubmitDirect 示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 创建此示例的批处理提交部分的以下输出文件夹。  

      \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\Out  

   - 编译的各种[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  

   - 注册 Submit 适配器使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置和发送端口和接收端口。  

     > [!NOTE]
     >  此示例将显示以下警告时创建并绑定端口：  
     >   
     >  `Warning: Receive handler not specified for receive location "SubmitDirectRL"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.ProcessRequest.Multiplier"; updating with first available host.`  
     >   
     >  您可以放心地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用接收位置，并启动发送端口和业务流程。  

     > [!NOTE]
     >  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
     > 
     > [!NOTE]
     >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
     > 
     > [!NOTE]
     >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="running-the-sample"></a>运行示例  
 由于此示例使用文件适配器，必须在运行 BizTalk 主机 (BizTalkServerApplication)。 使用以下过程运行 SubmitDirect 示例。  

#### <a name="to-run-the-batch-submission-portion-of-the-submitdirect-sample"></a>若要运行 SubmitDirect 示例的批处理提交部分  

1.  在命令窗口中，导航到以下文件夹：  

     \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\SubmitMessages\bin\Debug  

2.  运行文件 SubmitMessages.exe，在命令行上传递多个字符串。  

     例如：SubmitMessages msg1 msg2 msg3  

3.  查看在 Out 输出文件夹中创建的多个文本文件。这些文件包含传递的命令行中，每个文件的其中一个字符串。  

#### <a name="to-run-the-requestresponse-portion-of-the-submitdirect-sample"></a>若要运行的请求/响应一部分 SubmitDirect 示例  

1.  在命令窗口中，导航到以下文件夹：  

     \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\SubmitRequest\bin\Debug  

2.  运行文件 SubmitRequest.exe，在命令行上传递相应的.xml 文件的名称。  

     例如：SubmitRequest ..\\..\DocInstance.xml  

3.  观察包含乘法运算，向控制台显示的结果的响应 XML 消息。  

## <a name="comments"></a>注释  
 其他应用程序中，可以使用 Submit 适配器。 可以从任何使用它。基于 NET 的代码，以将消息提交给你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以编程方式。 若要使用此适配器与您的代码，使用以下过程。  

#### <a name="to-use-the-sample-adapter-with-your-code"></a>若要使用与您的代码示例适配器  

1. 注册 Submit 适配器与你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果您运行此示例随附的 Setup.bat 文件，适配器应已注册并可供使用。 否则，您可以通过生成项目 TransportProxyUtils.csproj、 TransportProxyUtilsUI.csproj 和 TransportProxyUtilsReg.csproj，然后运行可执行文件生成的后一种的项目中，RegisterAdapter.exe 注册它。  

   > [!IMPORTANT]
   >  如果在 64 位计算机上安装 BizTalk，将 HKEY_CLASSES_ROOT\CLSID\ 注册表项的所有实例都更改为 hkey_classes_root\wow6432node\clsid \ 中**RegisterAdapter.cs**文件。  

2. 与使用 Submit 适配器的接收位置创建一个接收端口。 指定接收位置的地址。 地址可以是任何字符串都使用此适配器的接收位置中是唯一的。  

3. 引用程序集 Microsoft.BizTalk.SDKSamples.AdaptersDevelopment.TransportProxyUtils.dll 中你[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。  

4. 将消息提交给你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用一个或多个以下方法提供的此程序集。  


   |                                                方法                                                |                                                                                                                                                                                       Description                                                                                                                                                                                       |
   |---------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       **SubmitMessage()**<br /><br /> **BeginSubmitMessage()**<br /><br /> **EndSubmitMessage()**       |              同步和异步方法以单向消息提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 必须在消息上下文设置接收位置提交消息时的地址。<br /><br /> 返回一个布尔值，该值提交 （成功/失败） 的状态。              |
   |     **SubmitMessages()**<br /><br /> **BeginSubmitMessages()**<br /><br /> **EndSubmitMessages()**      | 同步和异步方法的单向消息数组提交[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 应在消息上下文上设置位置提交消息的接收位置的地址。<br /><br /> 返回一个布尔值，该值提交 （成功/失败） 的状态。 |
   | **SubmitSyncMessage()**<br /><br /> **BeginSubmitSyncMessage()**<br /><br /> **EndSubmitSyncMessage()** |                                     同步和异步方法来提交请求消息到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 应在消息上下文设置接收位置提交消息时的地址。<br /><br /> 返回响应消息。                                      |
   |                                      **CreateMessageFromString()**                                      |                                                                     创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从字符串的消息对象和消息上下文中设定接收位置地址属性。<br /><br /> 返回一个 BizTalk 消息对象。                                                                      |
   |                                      **CreateMessageFromStream()**                                      |                                创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从流的消息对象和消息上下文中设定接收位置地址属性。<br /><br /> 返回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息对象。                                |

    有关参数和这些方法的返回类型的详细信息，请参阅 MessagingAPIInterface.cs TransportProxyUtils 文件夹中的文件。  

## <a name="see-also"></a>请参阅  
 [适配器示例-开发](../core/adapter-samples-development.md)   
 [注册适配器](../core/registering-an-adapter.md)