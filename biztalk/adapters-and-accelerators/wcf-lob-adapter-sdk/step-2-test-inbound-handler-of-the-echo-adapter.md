---
title: 第 2 步：测试 Echo 适配器的入站处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f238a6ddafb70aa30d8b736042e48b0466b77a42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363261"
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a>第 2 步：测试 Echo 适配器的入站处理程序
![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **若要完成的时间：** 10 分钟。  
  
 在此步骤中，测试 Echo 适配器提供的入站的服务。 为此，使用 Visual Studio 中，添加适配器服务参考 Visual Studio 插件和自定义代码。  
  
## <a name="prerequisites"></a>先决条件  
 若要完成此步骤中，你必须完成[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。 完成此步骤可以独立于[步骤 1:测试 Echo 适配器的出站处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)。  
  
## <a name="create-a-visual-studio-project"></a>创建 Visual Studio 项目  
  
1.  启动 Visual Studio。  
  
2.  在 Visual Studio 中，在**文件**菜单，依次指向**新建**，然后单击**项目**。  
  
3.  在中**新的项目**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**项目类型**|单击**Visual C#**。|  
    |**模板**|单击**控制台应用程序**。|  
    |**名称**|类型**ConsumeEchoAdapter_Inbound**。|  
    |**位置**|类型**C:\Tutorials**。|  
    |**解决方案名称**|类型**ConsumeEchoAdapter_Inbound**。|  
  
4.  单击“确定” 。  
  
5.  在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  
  
## <a name="browse-search-and-generate-the-wcf-service"></a>浏览、 搜索和生成的 WCF 服务  
  
1.  在 Visual Studio 解决方案窗格中，右键单击**ConsumeEchoAdapter_Inbound**项目，然后选择**添加适配器服务引用**以启动添加适配器服务引用插件。  
  
2.  在中**添加适配器服务引用**屏幕上，选择一个绑定。 这可通过选择**echoAdapterBindingV2**。  
  
3.  接下来，通过单击配置的适配器和 connection 属性**配置**。  这将打开**配置适配器**屏幕。  
  
4.  在中**配置适配器**屏幕上，选择**绑定属性**选项卡以配置适配器属性。 请注意，自定义 Echo 适配器类别**入站**并**杂项**显示。 下**杂项**类别中，单击**InboundFileSystemWatcherFolder** ，然后输入你想要监视的目录。  
  
5.  单击**确定**以关闭**配置适配器**屏幕上，并返回到**添加适配器服务引用**屏幕。  
  
6.  接下来，单击**Connect**连接到 Echo 适配器 （和假设它支持的业务线系统）。 几分钟后，连接状态应更改为**已连接**和类别树 (下**选择一个类别**) 应填充。  
  
7.  若要查看可用的入站的操作，请更改**服务协定类型**到**服务 （入站操作）**。  
  
8.  在类别树中，单击**主类别**。 这将填充可用类别和与单个的入站操作的操作的列表。 没有类别。  
  
9. 在中**可用类别和操作**，选择**OnReceiveEcho**操作。 单击**添加**以使生成的 WCF 接口的所选的操作部分。  
  
10. 单击**确定**生成 WCF 接口。 这将应用程序配置文件 (app.config)、 WCF 接口 (EchoAdapterBindingInterface.cs) 和 WCF 服务 (EchoAdapterBindingService.cs) 添加到项目中。  
  
11. 单击**文件**上**Visual Studio**菜单，然后选择**全部保存**。  
  
## <a name="test-the-echo-adapter"></a>测试 Echo 适配器  
  
1.  在解决方案资源管理器中双击**EchoAdapterBindingService.cs**文件。  
  
2.  在 Visual Studio 编辑器中，内部**OnReceiveEcho**方法，用以下代码替换现有的实现：  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  在解决方案资源管理器中双击**Program.cs**文件。  
  
4.  在 Visual Studio 编辑器中，在 Main 方法中，添加以下代码以承载 WCF 服务。  
  
    ```csharp  
    try  
    {  
        // Create a ServiceHost for the EchoServiceImpl type  
        // and use the base address from app.config  
        System.ServiceModel.ServiceHost host = new System.ServiceModel.ServiceHost(typeof(EchoAdapterBindingNamespace.EchoAdapterBindingService));  
  
        // Open the ServiceHost to start listening for messages  
        host.Open();  
  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost  
        host.Close();  
    }  
    catch (TimeoutException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    catch (System.ServiceModel.CommunicationException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    ```  
  
5.  在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。  
  
6.  按 F5 以启动示例。  
  
7.  放入在本教程前面指定的目录的"txt"扩展名的文件。 应看到类似于程序输出窗口中的以下信息：  
  
     **服务已准备就绪。**  
  
     **按\<ENTER\>以终止服务。**  
  
     **路径 = file:///C:/Tutorial/InboundTest/InboundTest.txt，len = 229179**  
  
8.  按 Enter 键以停止服务。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您创建的测试应用程序对于开发中的公开 Echo 适配器的入站的操作[教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。 若要执行此操作，创建了一个 Visual Studio 项目，生成 WCF 服务，，并提供代码以承载 WCF 服务。 最后，您运行了测试应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 这是本教程的最后一步。 入站操作的详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.IInboundHandler`。 若要查看示例演示如何承载需要进行身份验证的 WCF 服务的 SDK，下载在 echo 适配器和测试代码[ http://go.microsoft.com/fwlink/?LinkID=96184 ](http://go.microsoft.com/fwlink/?LinkID=96184)。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：使用通过.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [教程 1:开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)