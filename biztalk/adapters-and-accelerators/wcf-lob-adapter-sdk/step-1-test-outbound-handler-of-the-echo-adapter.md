---
title: "步骤 1： 测试的 Echo 适配器的出站处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bf419a8ae3e6611f3d071cc94d274a5f2b0e00f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a>步骤 1： 测试 Echo 适配器的出站处理的程序
![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **完成时间：** 15 分钟  
  
 在此步骤中，你将测试由 Echo 适配器提供的三个出站操作。 你将使用执行此类情况的操作[!INCLUDE[vs2010](../../includes/vs2010-md.md)]，添加适配器服务引用 Visual Studio 插件和自定义代码。  
  
## <a name="prerequisites"></a>先决条件  
 若要完成此步骤，你必须已完成[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。  
  
## <a name="create-a-visual-studio-project"></a>创建 Visual Studio 项目  
  
1.  启动 Visual Studio。  
  
2.  在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。  
  
3.  在**新项目**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**项目类型**|单击**Visual C#**。|  
    |**模板**|单击**控制台应用程序**。|  
    |**名称**|类型**ConsumeEchoAdapter_Outbound**。|  
    |**位置**|类型**C:\Tutorials**。|  
    |**解决方案名称**|类型**ConsumeEchoAdapter_Outbound**。|  
  
4.  单击 **“确定”**。  
  
5.  在 Visual Studio 中，在**文件**菜单上，单击**保存所有**。  
  
## <a name="browse-search-and-generate-the-wcf-client"></a>浏览、 搜索和生成 WCF 客户端  
  
1.  在 Visual Studio 解决方案窗格中，右键单击**ConsumeEchoAdapter_Outbound**项目，然后选择**添加适配器服务引用**以启动添加适配器服务引用插件。  
  
2.  在**添加适配器服务引用**屏幕上，选择一个绑定。 这可通过选择**echoAdapterBindingV2**。  
  
3.  接下来，通过单击配置的适配器和连接属性**配置...**.  此时会弹出**配置适配器**屏幕。  
  
4.  在**配置适配器**屏幕上，选择**URI 属性**选项卡来配置连接属性。 请注意，显示了自定义的 Echo 适配器类别-**连接**和**格式**。 下**格式**类别中，更改**EchoInUpperCase**到**True**。  
  
5.  在**配置适配器**屏幕上，选择**绑定属性**选项卡来配置适配器属性。 请注意，自定义的 Echo 适配器类别**入站**和**杂项**显示。 下**杂项**类别中，更改**计数**到**3**。  
  
6.  单击**确定**关闭**配置适配器**屏幕并返回到**添加适配器服务引用**屏幕。  
  
7.  接下来，单击**连接**连接到 Echo 适配器 （及假设它支持的业务线系统）。 几分钟后的连接状态应更改为**已连接**和类别树 (下**选择类别**) 应进行填充。  
  
8.  在类别树中，单击**Main 类别**。 这将填充可用类别和与三个出站操作的操作的列表。 不将任何类别。  
  
    > [!NOTE]
    >  默认协定类型为出站。 类别结果将与此协定类型匹配。  
  
9. 在**可用类别和操作**，选择所有三个操作。 当存在大量的操作时，你可能使用搜索来缩小选择;在这种情况下，有仅三个。 单击**添加**以使生成的 WCF 接口的所选的操作部分。  
  
10. 单击**确定**生成 WCF 接口。 这将添加到项目的应用程序配置文件 (app.config) 和 WCF 客户端代理 (EchoAdapterBindingClient.cs)。  
  
11. 单击**文件**Visual Studio 菜单上，选择**保存所有**。  
  
## <a name="configure-adapter-authentication"></a>配置适配器身份验证  
  
1.  在 Visual Studio 解决方案窗格中，双击**app.config**。  
  
2.  查找`address`属性中`endpoint`元素。 该属性应与下面类似：  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     更改**enableAuthentication**从**False**到**True**如下所示。 这将需要调用应用程序中，可以将凭据传递给适配器。  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  通过单击保存解决方案**文件**在 Visual Studio 菜单，选择**保存所有**。  
  
## <a name="create-a-sample-xml-file"></a>创建示例 XML 文件  
  
1.  启动记事本实例。 使用开始菜单中，单击**所有程序**&#124;**附件**，然后选择**记事本**。  
  
2.  将下面的示例数据复制到记事本编辑器。  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <ns0:greeting xmlns:ns0="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes">  
      <ns0:address>  
        <ns0:street1>123 Microsoft Way</ns0:street1>  
        <ns0:street2>Building # 4599</ns0:street2>  
        <ns0:city>Redmond</ns0:city>  
        <ns0:state>WA</ns0:state>  
        <ns0:zip>98052</ns0:zip>  
      </ns0:address>  
      <ns0:greetingText>Welcome to Redmond!</ns0:greetingText>  
    </ns0:greeting>              
    ```  
  
3.  在记事本菜单上，单击**文件**，然后选择**另存为...**. 在"CustomGreetingInstance.xml"中键入的文件名称和选择的编码的 Unicode 和将其保存到项目目录中或另一个合适的位置。 请注意的完整路径和文件名以供稍后参考。  
  
4.  已成功保存该文件，请关闭文本编辑器。  
  
## <a name="test-the-echo-adapter"></a>测试 Echo 适配器  
  
1.  在解决方案资源管理器中，双击**Program.cs**文件。  
  
2.  在 Visual Studio 编辑器中，内部**Main**方法，添加以下代码行以创建生成的 WCF 客户端的实例。  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  现在添加建立为适配器的凭据的代码。 Echo 适配器中启用身份验证时，它将检查用户名存在的连接，但不是会检查值。  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  通过添加代码以调用 EchoStrings 操作继续进行。  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  通过添加代码以调用 EchoGreetings 操作继续进行。  
  
    ```csharp  
    // Invoke EchoGreetings()  
    Console.WriteLine("\nInvoking EchoGreetings() method against the adapter...");  
    microsoft.adapters.samples.echov2.Types.Greeting greeting = new microsoft.adapters.samples.echov2.Types.Greeting();  
    greeting.id = Guid.NewGuid();  
    greeting.sentDateTime = DateTime.Now;  
    greeting.greetingText = "Hello World!";  
    greeting.name = new microsoft.adapters.samples.echov2.Types.Name();  
    greeting.name.salutation = microsoft.adapters.samples.echov2.Types.Salutation.Miss;  
    greeting.name.firstName = "Jane";  
    greeting.name.middleName = "Z.";  
    greeting.name.lastName = "Smith";  
    microsoft.adapters.samples.echov2.Types.Greeting[] greetingArray = client.EchoGreetings(greeting);  
    foreach (microsoft.adapters.samples.echov2.Types.Greeting data in greetingArray)  
    {  
        Console.WriteLine(data.id + " " + data.sentDateTime + " " + data.greetingText + " " + data.name.firstName );  
    }  
    ```  
  
6.  通过添加代码以调用 EchoCustomGreetingsFromFile 操作继续进行。  
  
    ```csharp  
    // Invoke EchoCustomGreetingFromFile()  
    Console.WriteLine("\nInvoking EchoCustomGreetingFromFile() method against the adapter ...");  
    // Copy the sample data from CustomGreeting-instance.xml file and place in appropriate folder  
    // as specified in the operation parameter  
    microsoft.adapters.samples.echov2.PreDefinedTypes.CustomGreeting   
    // change the Uri to point to the greeting instance xml file you created  
    customGreeting = client.EchoCustomGreetingFromFile(new Uri(@"c:\CustomGreetingInstance.xml"));  
    Console.WriteLine(customGreeting.greetingText + " " + customGreeting.address.city);  
    client.Close();  
    Console.ReadLine();  
    ```  
  
7.  在 EchoCustomGreetingsFromFile 测试代码中，请确保自定义问候语使用你在前一过程中创建的文件。 更改代码以反映你的文件的位置。  
  
8.  在[!INCLUDE[vs2010](../../includes/vs2010-md.md)]上**文件**菜单上，单击**保存所有**。  
  
9. 运行该应用程序。 你应看到类似于下面的输出：  
  
     **对适配器调用 EchoStrings() 方法...**  
  
     **Bonjour ！**  
  
     **Bonjour ！**  
  
     **Bonjour ！**  
  
     **Bonjour ！**  
  
     **Bonjour ！**  
  
     **对适配器调用 EchoGreetings() 方法...**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**  
  
     **179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日下午 3:18:07 Hello World ！Jane**  
  
     **对适配器调用 EchoCustomGreetingFromFile() 方法...**  
  
     **欢迎使用 Redmond ！Redmond**  
  
10. 按 Enter 键停止节目。  
  
## <a name="what-did-i-just-do"></a>未我只需做什么？  
 在此步骤中，你创建的测试应用程序开发在教程 1 中的 Echo 适配器公开的三个出站操作。 为此，你创建了 Visual Studio 项目，生成 WCF 服务，并提供代码以承载 WCF 服务。 最后，您运行测试应用程序。  
  
## <a name="next-steps"></a>后续步骤  
 若要测试的入站的操作，请继续执行到[步骤 2： 测试入站处理程序回显适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
  [教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [步骤 2： 测试入站的回显适配器处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)