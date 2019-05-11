---
title: 第 1 步：创建单元测试，以提交到 BizTalk Server 文档 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688b14e4-bb16-4d12-86b8-37b8b6808472
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfd70b3b7c5e79940cbf2f877d2a01dcecf5541f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394600"
---
# <a name="step-1-create-a-unit-test-to-submit-documents-to-biztalk-server"></a><span data-ttu-id="b2a79-102">第 1 步：创建单元测试，以将文档提交给 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b2a79-102">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>
<span data-ttu-id="b2a79-103">计算机应用程序服务器，例如 BizTalk Server 用于执行特定任务代表的用户。</span><span class="sxs-lookup"><span data-stu-id="b2a79-103">Computer application servers such as BizTalk Server are designed to perform particular tasks on behalf of users.</span></span> <span data-ttu-id="b2a79-104">这些任务都是作为符合标准的应用程序服务器能够识别，通过应用程序服务器能够理解的协议的消息发送到应用程序服务器的客户端请求启动。</span><span class="sxs-lookup"><span data-stu-id="b2a79-104">These tasks are initiated as client requests sent to the application server as messages that conform to a standard that the application server understands, via a protocol that the application server understands.</span></span> <span data-ttu-id="b2a79-105">例如，客户端可能通过发送 internet 电子邮件通过 SMTP 协议的电子邮件服务器启动电子邮件的处理。</span><span class="sxs-lookup"><span data-stu-id="b2a79-105">For example, clients may initiate processing of email by sending internet e-mail messages to an email server via the SMTP protocol.</span></span> <span data-ttu-id="b2a79-106">同样，web 服务器处理客户端 HTML 或 ASP 请求，数据库服务器处理的 SQL 客户端请求和 BizTalk Server 可以处理符合使用许多行业标准协议的多个行业消息标准设置格式的客户端消息。</span><span class="sxs-lookup"><span data-stu-id="b2a79-106">Likewise, web servers process client HTML or ASP requests, database servers process client SQL requests and BizTalk Server can process client messages formatted in compliance with multiple industry message standards using numerous industry standard protocols.</span></span> <span data-ttu-id="b2a79-107">应用程序服务器的工作负荷容量通常应用程序服务器可以在给定的时间段内处理的消息数来度量。</span><span class="sxs-lookup"><span data-stu-id="b2a79-107">The workload capacity of an application server is typically measured by the number of messages that the application server can process in a given time period.</span></span> <span data-ttu-id="b2a79-108">BizTalk Server 的工作负荷容量，则同样认为的"每秒接收的文档"、"每秒处理的文档"和/或"每秒完成的业务流程"的平均数目扩展一段时间，如忙 workday 或甚至工作周。</span><span class="sxs-lookup"><span data-stu-id="b2a79-108">The workload capacity of BizTalk Server is likewise measured as the average number of “documents received per second”, “documents processed per second” and/or “orchestrations completed per second” over an extended period of time, such as a busy workday or even a work week.</span></span> <span data-ttu-id="b2a79-109">Visual Studio 2010 负载测试功能可以模拟多达数百个用户同时访问服务器应用程序的负载配置文件。</span><span class="sxs-lookup"><span data-stu-id="b2a79-109">Visual Studio 2010 load test functionality can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="b2a79-110">此负载测试功能提供了所选的关键性能指标，以及能够以供未来分析数据库中存储这些指标的实时度量值。</span><span class="sxs-lookup"><span data-stu-id="b2a79-110">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="b2a79-111">本文档介绍使用 Visual Studio 测试项目在负载测试 BizTalk Server 应用程序，包括如何创建单元测试，如何创建负载测试和所需的如何配置负载测试以捕获性能计数器数据确定 BizTalk Server 应用程序的最大可承受吞吐量 (MST)。</span><span class="sxs-lookup"><span data-stu-id="b2a79-111">This document desribes the use of Visual Studio Test projects for the purpose of load testing a BizTalk Server application, including how to create unit tests, how to create load tests and how to configure load tests to capture performance counter data required to determine the Maximum Sustainable Throughput (MST) of a BizTalk Server application.</span></span>  
  
## <a name="creating-a-visual-studio-unit-test-to-submit-documents-to-biztalk-server"></a><span data-ttu-id="b2a79-112">创建 Visual Studio 单元测试可将文档提交给 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b2a79-112">Creating a Visual Studio Unit Test to Submit Documents to BizTalk Server</span></span>  
 <span data-ttu-id="b2a79-113">Visual Studio 单元测试引用[Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293)命名空间提供支持单元测试的几个类。</span><span class="sxs-lookup"><span data-stu-id="b2a79-113">A Visual Studio Unit test references the [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) namespace which supplies several classes that provide support for unit testing.</span></span> <span data-ttu-id="b2a79-114">尤其重要[UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293)命名空间包括[Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID=208233)类来存储信息提供给单元测试并[Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID=208235)类用于定义测试方法。</span><span class="sxs-lookup"><span data-stu-id="b2a79-114">Of particular importance, the [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) namespace includes the [Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID=208233) class to store information provided to Unit tests and the [Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID=208235) class is used to define Test methods.</span></span> <span data-ttu-id="b2a79-115">对于负载测试 BizTalk Server，测试方法应指定要加载的消息和消息应发送到终结点/URL。</span><span class="sxs-lookup"><span data-stu-id="b2a79-115">For purposes of load testing BizTalk Server, Test methods should specify the message to be loaded and the endpoint/URL to which the message should be sent.</span></span> <span data-ttu-id="b2a79-116">因为这会创建相应的 BizTalk 接收位置时 BizTalk Server 的消息入口点，然后将提供终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="b2a79-116">The endpoint/URL will then serve as the message entry point into BizTalk Server when a corresponding BizTalk receive location is created.</span></span>  
  
 <span data-ttu-id="b2a79-117">为便于说明，本主题中的示例代码介绍了使用测试方法[System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID=208238)类，以将消息发送到使用 WCF 的服务终结点net.tcp 终结点并监视由 BizTalk Wcf-custom 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="b2a79-117">For purposes of illustration, the sample code in this topic describes Test methods which utilize the [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID=208238) class to send messages to service endpoints that use the WCF net.tcp endpoint and are monitored by the BizTalk WCF-Custom receive adapter.</span></span> <span data-ttu-id="b2a79-118">测试项目的应用程序配置 (app.config) 文件中定义的测试消息的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="b2a79-118">Service endpoints for test messages are defined in the Application Configuration (app.config) file of the Test project.</span></span>  
  
 <span data-ttu-id="b2a79-119">有关 Visual Studio 单元测试的详细信息请参阅[的单元测试剖析](http://go.microsoft.com/fwlink/?LinkID=208232)(http://go.microsoft.com/fwlink/?LinkID=208232)。</span><span class="sxs-lookup"><span data-stu-id="b2a79-119">For more information about Visual Studio Unit Tests see [Anatomy of a Unit Test](http://go.microsoft.com/fwlink/?LinkID=208232) (http://go.microsoft.com/fwlink/?LinkID=208232).</span></span>  
  
 <span data-ttu-id="b2a79-120">请执行以下各节中的步骤，以使用单元测试可将文档提交给一个或多个 BizTalk Server 计算机创建测试项目。</span><span class="sxs-lookup"><span data-stu-id="b2a79-120">Follow the steps in the sections below to create a Test project with a Unit Test to submit documents to one or more BizTalk Server computers.</span></span> <span data-ttu-id="b2a79-121">已完成这些步骤，使用 Visual Studio 2010 Ultimate Edition。</span><span class="sxs-lookup"><span data-stu-id="b2a79-121">These steps were completed using Visual Studio 2010 Ultimate Edition.</span></span>  
  
### <a name="set-visual-studio-2010-test-project-options"></a><span data-ttu-id="b2a79-122">设置 Visual Studio 2010 测试项目选项</span><span class="sxs-lookup"><span data-stu-id="b2a79-122">Set Visual Studio 2010 Test Project Options</span></span>  
  
1.  <span data-ttu-id="b2a79-123">启动 Visual Studio 2010 Ultimate edition。</span><span class="sxs-lookup"><span data-stu-id="b2a79-123">Launch Visual Studio 2010 Ultimate edition.</span></span> <span data-ttu-id="b2a79-124">单击**启动**，依次指向**所有程序**，指向**Microsoft Visual Studio 2010** ，然后单击**Microsoft Visual Studio 2010**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-124">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2010** and then click **Microsoft Visual Studio 2010**.</span></span>  
  
2.  <span data-ttu-id="b2a79-125">在 Visual Studio 2010 中，单击**工具**，然后单击**选项**以显示**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="b2a79-125">In Visual Studio 2010, click **Tools** and then click **Options** to display the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="b2a79-126">单击此项可展开**测试工具**，然后单击**测试项目**以显示用于创建新测试项目的选项。</span><span class="sxs-lookup"><span data-stu-id="b2a79-126">Click to expand **Test Tools** and then click **Test Project** to display options for creation of new test projects.</span></span>  
  
4.  <span data-ttu-id="b2a79-127">设置**默认测试项目语言：** 到**VisualC#测试项目**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-127">Set the **Default test project language:** to **Visual C# test project**.</span></span>  
  
5.  <span data-ttu-id="b2a79-128">在选项下**选择将添加到每个新的测试项目，默认情况下的文件：** 选择**VisualC#测试项目**，并取消选中所有测试类型的视觉对象C#测试项目除**单元测试**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-128">Under the option to **Select the files that will be added to each new test project, by default:** select **Visual C# test project**, and uncheck all of the test types for Visual C# test projects except for **Unit Test**.</span></span>  
  
6.  <span data-ttu-id="b2a79-129">单击 **“确定”** 关闭 **“选项”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="b2a79-129">Click **OK** to close the **Options** dialog box.</span></span>  
  
### <a name="create-a-new-visual-studio-2010-solution-with-a-test-project"></a><span data-ttu-id="b2a79-130">使用测试项目中创建一个新的 Visual Studio 2010 解决方案</span><span class="sxs-lookup"><span data-stu-id="b2a79-130">Create a new Visual Studio 2010 Solution with a Test Project</span></span>  
  
1.  <span data-ttu-id="b2a79-131">创建文件夹**C:\Projects** Visual Studio 2010 Ultimate 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b2a79-131">Create the folder **C:\Projects** on the Visual Studio 2010 Ultimate computer.</span></span>  
  
2.  <span data-ttu-id="b2a79-132">在 Visual Studio 2010 中，单击**文件**，指向**新建**，然后单击**项目**以显示**新项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="b2a79-132">In Visual Studio 2010 click **File**, point to **New**, and click **Project** to display the **New Project** dialog box.</span></span>  
  
3.  <span data-ttu-id="b2a79-133">下**已安装的模板**单击此项可展开**Visual C#** ，然后单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-133">Under **Installed Templates** click to expand **Visual C#**, and click **Test**.</span></span>  
  
4.  <span data-ttu-id="b2a79-134">在底部**新的项目**对话框中指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="b2a79-134">At the bottom of the **New Project** dialog box specify the following options:</span></span>  
  
    -   <span data-ttu-id="b2a79-135">**名称：**</span><span class="sxs-lookup"><span data-stu-id="b2a79-135">**Name:**</span></span>  
         <span data-ttu-id="b2a79-136">**BTSLoad**</span><span class="sxs-lookup"><span data-stu-id="b2a79-136">**BTSLoad**</span></span>  
  
    -   <span data-ttu-id="b2a79-137">**位置：**</span><span class="sxs-lookup"><span data-stu-id="b2a79-137">**Location:**</span></span>  
         <span data-ttu-id="b2a79-138">**C:\Projects\\**</span><span class="sxs-lookup"><span data-stu-id="b2a79-138">**C:\Projects\\**</span></span>  
  
    -   <span data-ttu-id="b2a79-139">**解决方案名称：**</span><span class="sxs-lookup"><span data-stu-id="b2a79-139">**Solution name:**</span></span>  
         <span data-ttu-id="b2a79-140">**LoadTest**</span><span class="sxs-lookup"><span data-stu-id="b2a79-140">**LoadTest**</span></span>  
  
5.  <span data-ttu-id="b2a79-141">确保选项**创建解决方案目录**已选中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-141">Ensure that the option to **Create directory for solution** is checked and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b2a79-142">将文件夹添加到 BTSLoad 项目中;此文件夹将包含要提交到 BizTalk Server 的测试消息。</span><span class="sxs-lookup"><span data-stu-id="b2a79-142">Add a folder to the BTSLoad project; this folder will contain test messages to be submitted to BizTalk Server.</span></span> <span data-ttu-id="b2a79-143">在解决方案资源管理器，右键单击 BTSLoad 项目，指向**外**，然后单击**新文件夹**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-143">In Solution Explorer, right-click the BTSLoad project, point to **Add**, and click **New Folder**.</span></span> <span data-ttu-id="b2a79-144">突出显示的文本的文件夹图标**NewFolder1**将显示在 BTSLoad 项目下，类型**TestMessages**若要更改突出显示的文本并按**Enter**密钥若要创建文件夹 C:\Projects\LoadTest\BTSLoad\TestMessages。</span><span class="sxs-lookup"><span data-stu-id="b2a79-144">A folder icon with the highlighted text **NewFolder1** will appear under the BTSLoad project, type **TestMessages** to change the highlighted text and press the **Enter** key to create the folder C:\Projects\LoadTest\BTSLoad\TestMessages.</span></span>  
  
### <a name="update-the-code-in-the-test-project-and-add-an-application-configuration-file-to-the-test-project"></a><span data-ttu-id="b2a79-145">更新测试项目中的代码并将应用程序配置文件添加到测试项目</span><span class="sxs-lookup"><span data-stu-id="b2a79-145">Update the Code in the Test Project and add an Application Configuration File to the Test Project</span></span>  
  
1.  <span data-ttu-id="b2a79-146">在解决方案资源管理器中，单击以选择**UnitTest1.cs**和现有代码替换为以下示例代码列表：</span><span class="sxs-lookup"><span data-stu-id="b2a79-146">In Solution Explorer click to select **UnitTest1.cs** and replace the existing code with the following sample code listing:</span></span>  
  
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
  
2.  <span data-ttu-id="b2a79-147">将应用程序配置文件添加到测试项目：</span><span class="sxs-lookup"><span data-stu-id="b2a79-147">Add an Application Configuration file to the Test project:</span></span>  
  
    1.  <span data-ttu-id="b2a79-148">在解决方案资源管理器，右键单击 BTSLoad 项目，指向**外**然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-148">In Solution Explorer, right-click the BTSLoad project, point to **Add** and click **New item**.</span></span>  
  
    2.  <span data-ttu-id="b2a79-149">在中**添加新项**对话框中的**已安装的模板**，单击**常规**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-149">In the **Add New Item** dialog box, under **Installed Templates**, click **General**.</span></span>  
  
    3.  <span data-ttu-id="b2a79-150">在显示项列表中单击以选择**应用程序配置文件**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-150">In the list of items that are displayed click to select **Application Configuration File** and then click **Add**.</span></span>  
  
    4.  <span data-ttu-id="b2a79-151">在解决方案资源管理器中选择 app.config 文件和 app.config 文件的内容替换为下面列出的示例代码：</span><span class="sxs-lookup"><span data-stu-id="b2a79-151">In Solution Explorer select the app.config file and replace the contents of the app.config file with the sample code listing below:</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b2a79-152">在此文件中，定义每个客户端终结点*BizTalk Server 计算机*是 BizTalk Server 将执行的计算机进行负载测试针对的实际名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="b2a79-152">For each client endpoint defined in this file, *BizTalk Server Computer* is a placeholder for the actual name of the BizTalk Server computer(s) that you will perform load testing against.</span></span>  
  
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
  
    5.  <span data-ttu-id="b2a79-153">单击**文件**在 Visual Studio 2010，然后单击菜单**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-153">Click the **File** menu in Visual Studio 2010 and then click **Save All**.</span></span>  
  
### <a name="add-a-test-message-to-the-project"></a><span data-ttu-id="b2a79-154">将测试消息添加到项目</span><span class="sxs-lookup"><span data-stu-id="b2a79-154">Add a Test Message to the Project</span></span>  
 <span data-ttu-id="b2a79-155">对于此示例中，BizTalk Server 接收位置和发送端口将配置为使用通过管道传递，并且会执行任何文档验证。</span><span class="sxs-lookup"><span data-stu-id="b2a79-155">For purposes of this example, BizTalk Server receive location(s) and send port(s) will be configured to use pass through pipelines and will not perform any document validation.</span></span> <span data-ttu-id="b2a79-156">请按照下列步骤将测试消息添加到项目：</span><span class="sxs-lookup"><span data-stu-id="b2a79-156">Follow these steps to add a test message to the project:</span></span>  
  
1.  <span data-ttu-id="b2a79-157">启动记事本。</span><span class="sxs-lookup"><span data-stu-id="b2a79-157">Launch Notepad.</span></span> <span data-ttu-id="b2a79-158">单击**启动**，单击**运行**并键入**记事本**中**运行**对话框。</span><span class="sxs-lookup"><span data-stu-id="b2a79-158">Click **Start**, click **Run** and type **Notepad** in the **Run** dialog box.</span></span>  
  
2.  <span data-ttu-id="b2a79-159">将以下文本复制到记事本并将另存为"C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml"</span><span class="sxs-lookup"><span data-stu-id="b2a79-159">Copy the following text into Notepad and save as “C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml”</span></span>  
  
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
  
3.  <span data-ttu-id="b2a79-160">关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="b2a79-160">Close Notepad.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b2a79-161">此文件将需要保存到每个负载测试代理计算机上使用相同的文件名，如果使用多个负载测试代理计算机来进行负载测试的相同路径。</span><span class="sxs-lookup"><span data-stu-id="b2a79-161">This file will need to be saved to the same path using the same file name on every Load Test Agent computer if multiple Load Test Agent computers are used for load testing.</span></span>  
  
### <a name="add-necessary-references-to-the-project-and-build-the-test-project"></a><span data-ttu-id="b2a79-162">添加必要引用到项目并生成测试项目</span><span class="sxs-lookup"><span data-stu-id="b2a79-162">Add Necessary References to the Project and Build the Test Project</span></span>  
  
1.  <span data-ttu-id="b2a79-163">在解决方案资源管理器中右键单击**引用**BTSLoad 项目并单击文件夹**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="b2a79-163">In Solution Explorer, right-click the **References** folder for the BTSLoad project and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="b2a79-164">在添加引用对话框中，单击 **.NET**选项卡上，使用 CTRL + 单击键盘/鼠标组合同时选择以下.NET 命名空间：</span><span class="sxs-lookup"><span data-stu-id="b2a79-164">In the Add Reference dialog box, click the **.NET** tab and use the CTRL+Click keyboard/mouse combination to simultaneously select the following .NET namespaces:</span></span>  
  
    -   <span data-ttu-id="b2a79-165">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="b2a79-165">System.Configuration</span></span>  
  
    -   <span data-ttu-id="b2a79-166">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="b2a79-166">System.Runtime.Serialization</span></span>  
  
    -   <span data-ttu-id="b2a79-167">System.ServiceModel.Channels</span><span class="sxs-lookup"><span data-stu-id="b2a79-167">System.ServiceModel.Channels</span></span>  
  
    -   <span data-ttu-id="b2a79-168">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b2a79-168">System.ServiceModel</span></span>  
  
    -   <span data-ttu-id="b2a79-169">System.Web.Extensions</span><span class="sxs-lookup"><span data-stu-id="b2a79-169">System.Web.Extensions</span></span>  
  
    -   <span data-ttu-id="b2a79-170">System.Xml</span><span class="sxs-lookup"><span data-stu-id="b2a79-170">System.Xml</span></span>  
  
3.  <span data-ttu-id="b2a79-171">选择命名空间后单击**确定**将这些程序集添加为对 BTSLoad 测试项目的引用。</span><span class="sxs-lookup"><span data-stu-id="b2a79-171">After selecting the namespaces click **OK** to add these assemblies as references to the BTSLoad Test project.</span></span>  
  
4.  <span data-ttu-id="b2a79-172">右键单击**BTSLoad**项目，然后单击**生成**若要将项目编译为 BTSLoad 程序集。</span><span class="sxs-lookup"><span data-stu-id="b2a79-172">Right click the **BTSLoad** project and then click **Build** to compile the project into the BTSLoad assembly.</span></span>