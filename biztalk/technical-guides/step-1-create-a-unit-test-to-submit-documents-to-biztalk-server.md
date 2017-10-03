---
title: "步骤 1： 创建单元测试，以便提交给 BizTalk Server 文档 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 688b14e4-bb16-4d12-86b8-37b8b6808472
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8016bc237b55c2404a21c91e2e68d78fdd21bcf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-a-unit-test-to-submit-documents-to-biztalk-server"></a>步骤 1： 创建单元测试，以便提交给 BizTalk Server 文档
计算机应用程序服务器，例如 BizTalk Server 用于执行特定任务代表的用户。 这些任务都是作为一种标准，了解应用程序服务器，通过应用程序服务器理解协议符合消息发送到应用程序服务器的客户端请求启动。 例如，客户端可能通过发送 internet 电子邮件通过 SMTP 协议的电子邮件服务器启动的电子邮件的处理。 同样，web 服务器处理客户端 HTML 或 ASP 请求，数据库服务器处理客户端 SQL 请求并且 BizTalk Server 可以处理客户端消息符合使用大量的行业标准协议的多个行业消息标准格式。 通常可按应用程序服务器可以在给定的时间内处理的消息数衡量应用程序服务器的工作负载容量。 BizTalk Server 的工作负载容量同样以"每秒接收的文档"、"每秒处理的文档"和/或"每秒完成的业务流程"的平均数的时间，如忙 workday 甚至延长时期的工作周。 Visual Studio 2010 负载测试功能可以模拟数百个用户同时访问服务器应用程序的负载配置文件。 此负载测试功能提供了所选的关键性能指标，以及供将来分析数据库中存储这些指标的能力的实时度量值。 此文档介绍使用 Visual Studio 测试项目，用于负载测试 BizTalk Server 应用程序，包括如何创建单元测试，如何创建负载测试和所需如何配置负载测试以捕获性能计数器数据确定 BizTalk Server 应用程序的最大可持续吞吐量 (MST)。  
  
## <a name="creating-a-visual-studio-unit-test-to-submit-documents-to-biztalk-server"></a>创建 Visual Studio 单元测试，以便提交给 BizTalk Server 文档  
 Visual Studio 单元测试引用[Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) 命名空间提供支持单元测试的多个类。 非常重要， [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID = 132293) 命名空间包括[Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID = 208233) 类来存储信息提供给单元测试和[Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID = 208235) 类用于定义测试方法。 对于负载测试 BizTalk Server，测试方法应指定要加载的消息以及应将消息发送到的终结点/URL。 创建 BizTalk Server 时相应 BizTalk 接收位置的消息入口点，然后将提供终结点 URL。  
  
 有关演示目的，本主题中的示例代码文件介绍了利用测试方法[System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID = 208238) 类将消息发送到使用 WCF net.tcp 终结点和监视通过 BizTalk WCF 自定义的服务终结点接收适配器。 测试项目中的应用程序配置 (app.config) 文件中定义的测试消息的服务终结点。  
  
 有关 Visual Studio 单元测试的详细信息请参阅[单元测试的剖析](http://go.microsoft.com/fwlink/?LinkID=208232)(http://go.microsoft.com/fwlink/?LinkID=208232)。  
  
 按照以下各节中的步骤来使用单元测试，以便提交到一个或多个 BizTalk Server 计算机的文档创建测试项目。 完成这些步骤时使用 Visual Studio 2010 Ultimate Edition。  
  
### <a name="set-visual-studio-2010-test-project-options"></a>设置 Visual Studio 2010 测试项目选项  
  
1.  启动 Visual Studio 2010 旗舰版。 单击**启动**，指向**所有程序**，指向**Microsoft Visual Studio 2010** ，然后单击**Microsoft Visual Studio 2010**。  
  
2.  在 Visual Studio 2010 中，单击**工具**，然后单击**选项**以显示**选项**对话框。  
  
3.  单击以展开**测试工具**，然后单击**测试项目**以显示新的测试项目中创建的选项。  
  
4.  设置**默认测试项目语言：**到**Visual C# 测试项目**。  
  
5.  在选项下**选择将按默认添加到每个新的测试项目的文件：**选择**Visual C# 测试项目**，并取消选中的所有测试类型适用于 Visual C# 中的测试除外项目**单元测试**。  
  
6.  单击 **“确定”** 关闭 **“选项”** 对话框。  
  
### <a name="create-a-new-visual-studio-2010-solution-with-a-test-project"></a>使用测试项目中创建新的 Visual Studio 2010 解决方案  
  
1.  创建文件夹**C:\Projects** Visual Studio 2010 旗舰版的计算机上。  
  
2.  在 Visual Studio 2010 中，单击**文件**，指向**新建**，然后单击**项目**以显示**新项目**对话框。  
  
3.  下**已安装的模板**单击以展开**Visual C#**，然后单击**测试**。  
  
4.  在底部**新项目**对话框中指定以下选项：  
  
    -   **名称：**  
         **BTSLoad**  
  
    -   **位置：**  
         **C:\Projects\\**  
  
    -   **解决方案名称：**  
         **LoadTest**  
  
5.  确保选项**创建解决方案的目录**已选中，然后单击**确定**。  
  
6.  将文件夹添加到 BTSLoad 项目中;此文件夹将包含测试消息，若要提交到 BizTalk Server。 在解决方案资源管理器，右键单击 BTSLoad 项目，指向**添加**，然后单击**新文件夹**。 一个带有突出显示的文本的文件夹图标**NewFolder1**将出现在 BTSLoad 项目，类型**TestMessages**更改突出显示的文本和按**Enter**密钥若要创建文件夹 C:\Projects\LoadTest\BTSLoad\TestMessages。  
  
### <a name="update-the-code-in-the-test-project-and-add-an-application-configuration-file-to-the-test-project"></a>更新测试项目中的代码并将应用程序配置文件添加到测试项目  
  
1.  在解决方案资源管理器中，单击以选择**UnitTest1.cs**和将现有代码替换为下面的示例代码清单：  
  
    ```csharp  
    #region Using Directives  
    using System;  
    using System.IO;  
    using System.Diagnostics;  
    using System.Text;  
    using System.Configuration;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Xml;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using Microsoft.VisualStudio.TestTools.UnitTesting;  
    #endregion  
  
    namespace Microsoft.BizTalk.Samples  
    {  
        [TestClass]  
        public class BTSLoadTest  
        {  
            #region Constants  
            private const int MaxBufferSize = 2097152;  
            private const string Source = "BTS Load Test";  
            private const string Star = "*";  
            private const string TestMessageFolderParameter = "testMessageFolder";  
            private const string TestMessageFolderDefault = @"C:\Projects\LoadTest\BTSLoad\TestMessages";  
            private const string TestMessageFolderFormat = @"Test Message Folder = {0}";  
            private const string TestXmlDocument = "testxmldocument.xml";  
            #endregion  
  
            #region Private Instance Fields  
            private TestContext testContextInstance;  
            #endregion  
  
            #region Private ThreadStatic Fields  
            [ThreadStatic]  
            private static ChannelFactory<IRequestChannel> channelFactory;  
            [ThreadStatic]  
            private static IRequestChannel channel = null;  
            [ThreadStatic]  
            private static byte[] buffer = null;  
            #endregion  
  
            #region Private Static Fields  
            private static string testMessageFolder = null;  
            #endregion  
  
            #region Public Instance Constructor  
            public BTSLoadTest()  
            {  
            }  
            #endregion  
  
            #region Public Static Constructor  
            static BTSLoadTest()  
            {  
                try  
                {  
                    testMessageFolder = ConfigurationManager.AppSettings[TestMessageFolderParameter];  
                    if (string.IsNullOrEmpty(testMessageFolder))  
                    {  
                        testMessageFolder = TestMessageFolderDefault;  
                    }  
                }  
                catch (Exception ex)  
                {  
                    Trace.WriteLine(ex.Message);  
                    EventLog.WriteEntry(Source, ex.Message, EventLogEntryType.Error);  
                }  
            }  
            #endregion  
  
            #region Public Properties  
            /// <summary>  
            ///Gets or sets the test context which provides  
            ///information about and functionality for the current test run.  
            ///</summary>  
            public TestContext TestContext  
            {  
                get  
                {  
                    return testContextInstance;  
                }  
                set  
                {  
                    testContextInstance = value;  
                }  
            }  
            #endregion  
  
            #region Test Methods  
  
            [TestMethod]  
            public void BTSMessaging()  
            {  
                InvokeBizTalkReceiveLocation("BTSMessagingEP",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
  
            [TestMethod]  
            public void BTSMessaging2()  
            {  
                InvokeBizTalkReceiveLocation("BTSMessagingEP2",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
  
            [TestMethod]  
            public void BTSOrchestration()  
            {  
                InvokeBizTalkReceiveLocation("BTSOrchestrationEP",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
            #endregion  
  
            #region Helper Methods  
            public void InvokeBizTalkReceiveLocation(string endpointConfigurationName,  
                                               string requestMessageFolder,  
                                               string requestMessageName,  
                                               MessageVersion messageVersion,  
                                               SessionMode sessionMode)  
            {  
                XmlTextReader xmlTextReader = null;  
                Message requestMessage = null;  
                Message responseMessage = null;  
  
                try  
                {  
                    if (channel == null || channel.State != CommunicationState.Opened)  
                    {  
                        channelFactory = new ChannelFactory<IRequestChannel>(endpointConfigurationName);  
                        channelFactory.Endpoint.Contract.SessionMode = sessionMode;  
                        channel = channelFactory.CreateChannel();  
                    }  
                    if (buffer == null)  
                    {  
                        string path = Path.Combine(requestMessageFolder, requestMessageName);  
  
                        string message;  
                        using (StreamReader reader = new StreamReader(File.Open(path, FileMode.Open, FileAccess.Read, FileShare.Read)))  
                        {  
                            message = reader.ReadToEnd();  
                        }  
                        buffer = Encoding.UTF8.GetBytes(message);  
                    }  
                    MemoryStream stream = new MemoryStream(buffer);  
                    xmlTextReader = new XmlTextReader(stream);  
                    requestMessage = Message.CreateMessage(messageVersion, Star, xmlTextReader);  
                    TestContext.BeginTimer(requestMessageName);  
                    responseMessage = channel.Request(requestMessage);  
                }  
                catch (FaultException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (CommunicationException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (TimeoutException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (Exception ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                finally  
                {  
                    TestContext.EndTimer(requestMessageName);  
                    CloseObjects(xmlTextReader,  
                                 requestMessage,  
                                 responseMessage);  
                }  
            }  
  
            private void HandleException(Exception ex)  
            {  
                try  
                {  
                    Trace.WriteLine(ex.Message);  
                    EventLog.WriteEntry(Source, ex.Message, EventLogEntryType.Error);  
                }  
                catch (Exception)  
                {  
                }  
            }  
  
            private void CloseObjects(XmlTextReader xmlTextReader,  
                               Message requestMessage,  
                               Message responseMessage)  
            {  
                try  
                {  
                    if (xmlTextReader != null)  
                    {  
                        xmlTextReader.Close();  
                    }  
                    if (requestMessage != null)  
                    {  
                        requestMessage.Close();  
                    }  
                    if (responseMessage != null)  
                    {  
                        responseMessage.Close();  
                    }  
                }  
                catch (Exception)  
                {  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
2.  将应用程序配置文件添加到测试项目：  
  
    1.  在解决方案资源管理器，右键单击 BTSLoad 项目，指向**添加**单击**新项**。  
  
    2.  在**添加新项**对话框中，在**已安装的模板**，单击**常规**。  
  
    3.  显示的项列表中单击以选择**应用程序配置文件**，然后单击**添加**。  
  
    4.  在解决方案资源管理器中选择的 app.config 文件，并将 app.config 文件的内容替换为下面列出的示例代码：  
  
        > [!IMPORTANT]  
        >  在此文件中，定义每个客户端终结点*BizTalk 服务器计算机*是将执行的计算机负载测试对 BizTalk Server 的实际名称的占位符。  
  
        ```xml  
  
        <configuration>  
          <system.serviceModel>  
            <!-- Bindings used by client endpoints -->  
            <bindings>  
              <netTcpBinding>  
                <binding name="netTcpBinding" closeTimeout="01:10:00" openTimeout="01:10:00" receiveTimeout="01:10:00" sendTimeout="01:10:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="100" maxBufferPoolSize="1048576" maxBufferSize="10485760" maxConnections="400" maxReceivedMessageSize="10485760">  
                  <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />  
                  <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false" />  
                  <security mode="None">  
                    <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
                    <message clientCredentialType="Windows" />  
                  </security>  
                </binding>  
              </netTcpBinding>  
            </bindings>  
            <client>  
              <!-- Client endpoints used to exchange messages with WCF Receive Locations -->  
  
              <!-- BTSMessagingEP -->  
              <endpoint address="net.tcp://BizTalk Server Computer:8123/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSMessagingEP" />  
              <endpoint address="net.tcp://BizTalk Server Computer:8123/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSMessagingEP" />  
  
              <!-- BTSOrchestrationEP -->  
              <endpoint address="net.tcp://BizTalk Server Computer:8122/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSOrchestrationEP" />  
            </client>  
          </system.serviceModel>  
          <appSettings>  
            <!-- Folder containing test messages -->  
            <add key="testMessageFolder" value="C:\Projects\LoadTest\BTSLoad\TestMessages" />  
            <add key="ClientSettingsProvider.ServiceUri" value="" />  
          </appSettings>  
        </configuration>  
        ```  
  
    5.  单击**文件**在 Visual Studio 2010 和然后单击菜单**保存所有**。  
  
### <a name="add-a-test-message-to-the-project"></a>向项目中添加一条测试消息  
 此示例的目的，BizTalk Server 接收位置和发送端口将配置为使用通过管道传递，并且将不执行任何文档验证。 请按照下列步骤以向项目中添加一条测试消息：  
  
1.  启动记事本。 单击**启动**，单击**运行**和类型**记事本**中**运行**对话框。  
  
2.  将以下文本复制到记事本，并将另存为"C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml"  
  
    ```  
    <BTSLoadTest xmlns="http://Microsoft.BizTalk.Samples.BTSLoadTest">  
    <MessageText>  
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    </MessageText>  
    </BTSLoadTest>  
    ```  
  
3.  关闭记事本。  
  
> [!IMPORTANT]  
>  此文件需要保存到每个负载测试代理计算机上使用相同的文件名称，如果使用多个负载测试代理计算机来进行负载测试的同一路径。  
  
### <a name="add-necessary-references-to-the-project-and-build-the-test-project"></a>添加对项目的必需引用，并生成测试项目  
  
1.  在解决方案资源管理器，右键单击**引用**BTSLoad 项目，然后单击文件夹**添加引用**。  
  
2.  在添加引用对话框中，单击**.NET**选项卡，并使用 CTRL + 单击键盘/鼠标组合，可同时选择以下.NET 命名空间：  
  
    -   System.Configuration  
  
    -   System.Runtime.Serialization  
  
    -   System.ServiceModel.Channels  
  
    -   System.ServiceModel  
  
    -   System.web.extensions 的引用  
  
    -   System.Xml  
  
3.  选择命名空间后单击**确定**将这些程序集添加为对 BTSLoad 测试项目的引用。  
  
4.  右键单击**BTSLoad**项目，然后单击**生成**入 BTSLoad 程序集编译项目。