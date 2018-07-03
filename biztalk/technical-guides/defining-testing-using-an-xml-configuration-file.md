---
title: 定义测试使用 XML 配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8339bcf-26d7-4a43-b68e-c4220a7a851d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd869d69ca11a41daac459229d7b58684e43afe7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992942"
---
# <a name="defining-testing-using-an-xml-configuration-file"></a><span data-ttu-id="6964f-102">定义测试使用 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="6964f-102">Defining Testing Using an XML Configuration File</span></span>
<span data-ttu-id="6964f-103">BizUnit 提供两种方法来定义测试： 通过 XML 配置文件和 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="6964f-103">BizUnit offers two ways to define tests: via an XML configuration file and via an Excel worksheet.</span></span> <span data-ttu-id="6964f-104">本主题重点介绍使用 XML 配置文件以定义测试;但是，您还应注意 BizUnit SDK，因为它提供了如何定义 BizUnit 测试用例使用 Excel 的一个有趣示例。</span><span class="sxs-lookup"><span data-stu-id="6964f-104">This topic focuses on using an XML configuration file to define tests; however, you should also look at the BizUnit SDK, since it provides an interesting example of how to define BizUnit test cases using Excel.</span></span> <span data-ttu-id="6964f-105">此外，您可能希望调查 BizUnit 设计器工具，它提供用于快速创建 BizUnit 测试用例的 GUI。</span><span class="sxs-lookup"><span data-stu-id="6964f-105">In addition, you may wish to investigate the BizUnit Designer tool, which provides a GUI that allows for rapid creation of BizUnit test cases.</span></span> <span data-ttu-id="6964f-106">本主题概述了如何定义测试用例使用 XML 配置使用非常简化的方案。</span><span class="sxs-lookup"><span data-stu-id="6964f-106">This topic provides an overview of how to define test cases using XML configuration using a very simplified scenario.</span></span>  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a><span data-ttu-id="6964f-107">定义使用 XML 配置 BizUnit 测试用例的概述</span><span class="sxs-lookup"><span data-stu-id="6964f-107">Overview of defining a BizUnit test case using XML configuration</span></span>  
 <span data-ttu-id="6964f-108">如只是所述，简化了这种情况下，为便于说明。</span><span class="sxs-lookup"><span data-stu-id="6964f-108">As just stated, this scenario is simplified for purposes of illustration.</span></span> <span data-ttu-id="6964f-109">请考虑消息传送应用程序，例如如下图所示的一个示例。</span><span class="sxs-lookup"><span data-stu-id="6964f-109">Consider a sample messaging application such as the one illustrated below.</span></span> <span data-ttu-id="6964f-110">让我们认为正常功能行为，此应用程序是 BizTalk 接收 XML 文件通过文件接收位置，然后将它发送到基于订阅的相应订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="6964f-110">Let’s assume that normal functional behavior for this application is that BizTalk receives an XML file via a file receive location, it then sends it to an appropriate subscriber based on a subscription.</span></span> <span data-ttu-id="6964f-111">若要有效地验证此方案中很重要我们在测试中执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6964f-111">To validate this scenario effectively it is important that we perform the following steps in the test:</span></span>  
  
1. <span data-ttu-id="6964f-112">设置环境以确保其处于一致状态并准备好运行测试的：</span><span class="sxs-lookup"><span data-stu-id="6964f-112">Set up the environment to ensure that it is in a consistent state and ready for the test to be run:</span></span>  
  
   -   <span data-ttu-id="6964f-113">这是通过删除使用的两个文件位置中存在的任何文件。</span><span class="sxs-lookup"><span data-stu-id="6964f-113">This is done by deleting any files that are present in the two file locations used.</span></span>  
  
2. <span data-ttu-id="6964f-114">运行测试以验证功能：</span><span class="sxs-lookup"><span data-stu-id="6964f-114">Run the test to verify functionality:</span></span>  
  
   -   <span data-ttu-id="6964f-115">创建文件接收位置轮询一个有效的文件夹中 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="6964f-115">Create a valid XML message in the folder that the file receive location polls.</span></span>  
  
   -   <span data-ttu-id="6964f-116">验证正确的 XML 消息被置于出站文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="6964f-116">Validate that the correct XML message is placed in the outbound folder location.</span></span>  
  
   -   <span data-ttu-id="6964f-117">验证应涵盖的架构和消息的有效负载信息。</span><span class="sxs-lookup"><span data-stu-id="6964f-117">The validation should cover both the schema and the payload information for the message.</span></span> <span data-ttu-id="6964f-118">（通常几个键字段应进行检查。）</span><span class="sxs-lookup"><span data-stu-id="6964f-118">(Typically a couple of the key fields should be examined.)</span></span>  
  
3. <span data-ttu-id="6964f-119">清理环境以确保在环境处于相同状态之前执行的测试：</span><span class="sxs-lookup"><span data-stu-id="6964f-119">Clean up the environment to ensure that the environment is in the same state as before the test executed:</span></span>  
  
   -   <span data-ttu-id="6964f-120">删除使用的两个文件位置中存在的任何文件。</span><span class="sxs-lookup"><span data-stu-id="6964f-120">Delete any files that are present in the two file locations used.</span></span>  
  
   <span data-ttu-id="6964f-121">![示例 BizTalk 消息传送应用程序](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span><span class="sxs-lookup"><span data-stu-id="6964f-121">![Sample BizTalk Messaging Application](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span></span>  
   <span data-ttu-id="6964f-122">示例 BizTalk 消息传送应用程序</span><span class="sxs-lookup"><span data-stu-id="6964f-122">Sample BizTalk Messaging application</span></span>  
  
   <span data-ttu-id="6964f-123">每个测试用例开头和结尾的测试用例 XML 标记;测试名称参数将传递到这，此处所示。</span><span class="sxs-lookup"><span data-stu-id="6964f-123">Each test case begins and ends with the TestCase XML tag; the testName parameter is passed into this as indicated here.</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 <span data-ttu-id="6964f-124">然后，输入 TestSetup 阶段，在其中我们确保在环境处于一致状态以运行测试。</span><span class="sxs-lookup"><span data-stu-id="6964f-124">Then we enter the TestSetup phase, in which we ensure that the environment is in a consistent state to run the test.</span></span> <span data-ttu-id="6964f-125">在此示例中，我们 TestData 目录中删除任何包含的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="6964f-125">In this example, we delete any XML messages that are contained in our TestData directory.</span></span> <span data-ttu-id="6964f-126">这是使用**FileDeleteMultipleStep**。</span><span class="sxs-lookup"><span data-stu-id="6964f-126">This is done using the **FileDeleteMultipleStep**.</span></span>  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 <span data-ttu-id="6964f-127">然后输入什么是测试，测试执行阶段的最关键部分。</span><span class="sxs-lookup"><span data-stu-id="6964f-127">We then enter what is the most critical section of the test, the test execution stage.</span></span> <span data-ttu-id="6964f-128">此阶段可以包含多个测试步骤。</span><span class="sxs-lookup"><span data-stu-id="6964f-128">This stage can contain multiple test steps.</span></span> <span data-ttu-id="6964f-129">在此示例中我们使用 FileCreateStep 复制文档 (所示的 InDoc1.xml \<SourcePath\>标记) 使用该文件放到我们接收位置。</span><span class="sxs-lookup"><span data-stu-id="6964f-129">In this example we use the FileCreateStep to copy a document (InDoc1.xml which can be seen in the \<SourcePath\> tag) to a file drop which is used by our receive location.</span></span> <span data-ttu-id="6964f-130">务必要注意的是 BizUnit 支持使用在此步骤; 文件名唯一标识符这可以看到与 %creationpath 标记中的 Guid %引用。</span><span class="sxs-lookup"><span data-stu-id="6964f-130">It’s important to note that BizUnit supports using unique identifiers for filenames in this step; this can be seen with the %Guid% reference in the CreationPath tag.</span></span>  
  
 <span data-ttu-id="6964f-131">此操作完成后后，我们需要使用**FileValidateStep**若要验证出站消息已创建。</span><span class="sxs-lookup"><span data-stu-id="6964f-131">After this has been completed, we need to use the **FileValidateStep** to validate the outbound message has been created.</span></span> <span data-ttu-id="6964f-132">您将注意到此步骤允许您指定超时值 （这是以毫秒为单位）、 目录和搜索模式。</span><span class="sxs-lookup"><span data-stu-id="6964f-132">You will notice this step allows you to specify a timeout value (this is in milliseconds), the directory and the search pattern.</span></span> <span data-ttu-id="6964f-133">除此之外， **DeleteFile**标记可用于指定是否想要删除已验证的文件。</span><span class="sxs-lookup"><span data-stu-id="6964f-133">In addition to this, the **DeleteFile** tag enables you to specify whether you want the file to be removed after it has been validated.</span></span> <span data-ttu-id="6964f-134">最后，您还应注意验证包括 XPath 查询，验证 XML 消息 （它检查的值是 PONumber_0。） 中的 PONumber 节点检查和验证的任何出站消息的有效负载是使用 BizUnit 时应遵循的指导原则的另一个示例。</span><span class="sxs-lookup"><span data-stu-id="6964f-134">Finally, you should also note the validation includes an XPath query, which validates the PONumber node within the XML message (it checks that the value is PONumber_0.) Examination and validation of the payload of any outbound messages is another example of a guiding principle that you should follow when using BizUnit.</span></span>  
  
```  
<TestExecution>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileCreateStep">  
      <SourcePath>..\..\..\TestData\InDoc1.xml</SourcePath>  
      <CreationPath>..\..\..\Rec_03\TransactionId_%Guid%.xml</CreationPath>  
   </TestStep>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileValidateStep">  
      <Timeout>3000</Timeout>  
      <Directory>..\..\..\Rec_03\</Directory>  
      <SearchPattern>TransactionId_*.xml</SearchPattern>  
      <DeleteFile>true</DeleteFile>  
      <ValidationStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.XmlValidationStep">  
         <XmlSchemaPath>..\..\..\TestData\PurchaseOrder.xsd</XmlSchemaPath>  
         <XmlSchemaNameSpace>http://SendMail.PurchaseOrder</XmlSchemaNameSpace>  
         <XPathList>  
            <XPathValidation query="/*[local-name()='PurchaseOrder' and namespace-uri()='http://SendMail.PurchaseOrder']/*[local-name()='PONumber' and namespace-uri()='']">PONumber_0</XPathValidation>  
         </XPathList>  
      </ValidationStep>  
   </TestStep>  
</TestExecution>  
```  
  
 <span data-ttu-id="6964f-135">测试用例的最后一个阶段是清理。</span><span class="sxs-lookup"><span data-stu-id="6964f-135">The final stage of the test case is the cleanup.</span></span> <span data-ttu-id="6964f-136">在这里，可以看出**FileDelete**测试步骤用于清理测试所使用的目录。</span><span class="sxs-lookup"><span data-stu-id="6964f-136">As can be seen here, the **FileDelete** test step is used to clean up the directories used by the test.</span></span>  
  
```  
<TestCleanup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
      <SearchPattern>*.xml</SearchPattern>   
   </TestStep>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\Rec_03\</Directory>  
      <SearchPattern>*.xml</SearchPattern>   
   </TestStep>  
</TestCleanup>  
```  
  
 <span data-ttu-id="6964f-137">希望此示例说明在 BizUnit 中定义的测试的相对来说比较简单，并且，通过使用此测试框架，您将能够快速开发提供你的应用程序的功能测试的测试用例。</span><span class="sxs-lookup"><span data-stu-id="6964f-137">Hopefully this example illustrates that defining tests in BizUnit is relatively straightforward and that by using this test framework, you will be able to rapidly develop test cases to provide functional testing of your application.</span></span>  
  
### <a name="full-test-case-example"></a><span data-ttu-id="6964f-138">完整的测试用例示例</span><span class="sxs-lookup"><span data-stu-id="6964f-138">Full test case example</span></span>  
 <span data-ttu-id="6964f-139">完整的测试用例的配置文件内容包含了供你参考：</span><span class="sxs-lookup"><span data-stu-id="6964f-139">The full test case configuration file contents are included here for your reference:</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
   <TestSetup>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\TestData\</Directory>  
            <SearchPattern>*.xml</SearchPattern>   
         </TestStep>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileCreateStep">  
         <SourcePath>..\..\..\TestData\InDoc1.xml</SourcePath>  
         <CreationPath>..\..\..\Rec_03\TransactionId_%Guid%.xml</CreationPath>  
      </TestStep>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileValidateStep">  
         <Timeout>3000</Timeout>  
         <Directory>..\..\..\Rec_03\</Directory>  
         <SearchPattern>TransactionId_*.xml</SearchPattern>  
         <DeleteFile>true</DeleteFile>  
         <ValidationStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.XmlValidationStep">  
            <XmlSchemaPath>..\..\..\TestData\PurchaseOrder.xsd</XmlSchemaPath>  
            <XmlSchemaNameSpace>http://SendMail.PurchaseOrder</XmlSchemaNameSpace>  
            <XPathList>  
               <XPathValidation query="/*[local-name()='PurchaseOrder' and namespace-uri()='http://SendMail.PurchaseOrder']/*[local-name()='PONumber' and namespace-uri()='']">PONumber_0</XPathValidation>  
            </XPathList>  
         </ValidationStep>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
      <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
         <Directory>..\..\..\Rec_03\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6964f-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="6964f-140">See Also</span></span>  
 [<span data-ttu-id="6964f-141">使用 BizUnit 优化自动测试</span><span class="sxs-lookup"><span data-stu-id="6964f-141">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)