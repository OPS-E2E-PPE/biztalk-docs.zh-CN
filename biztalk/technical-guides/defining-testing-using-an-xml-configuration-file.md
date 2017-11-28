---
title: "定义测试使用 XML 配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8339bcf-26d7-4a43-b68e-c4220a7a851d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 761f8c0a4480c26240926240cd890c1c68419b58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defining-testing-using-an-xml-configuration-file"></a><span data-ttu-id="5232c-102">定义测试使用 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="5232c-102">Defining Testing Using an XML Configuration File</span></span>
<span data-ttu-id="5232c-103">BizUnit 提供两种方法来定义测试： 通过 XML 配置文件和通过 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="5232c-103">BizUnit offers two ways to define tests: via an XML configuration file and via an Excel worksheet.</span></span> <span data-ttu-id="5232c-104">本主题重点介绍使用 XML 配置文件来定义测试;但是，你还应注意 BizUnit SDK，因为它提供了如何定义使用 Excel BizUnit 测试用例的一个有趣示例。</span><span class="sxs-lookup"><span data-stu-id="5232c-104">This topic focuses on using an XML configuration file to define tests; however, you should also look at the BizUnit SDK, since it provides an interesting example of how to define BizUnit test cases using Excel.</span></span> <span data-ttu-id="5232c-105">此外，你可能希望调查 BizUnit 设计器工具，它提供一个 GUI，允许快速创建 BizUnit 测试用例。</span><span class="sxs-lookup"><span data-stu-id="5232c-105">In addition, you may wish to investigate the BizUnit Designer tool, which provides a GUI that allows for rapid creation of BizUnit test cases.</span></span> <span data-ttu-id="5232c-106">本主题概述了如何定义使用 XML 配置使用非常简化的方案的测试用例。</span><span class="sxs-lookup"><span data-stu-id="5232c-106">This topic provides an overview of how to define test cases using XML configuration using a very simplified scenario.</span></span>  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a><span data-ttu-id="5232c-107">定义 BizUnit 测试用例使用 XML 配置概述</span><span class="sxs-lookup"><span data-stu-id="5232c-107">Overview of defining a BizUnit test case using XML configuration</span></span>  
 <span data-ttu-id="5232c-108">如只需所述，这种情况下得到了简化，演示目的。</span><span class="sxs-lookup"><span data-stu-id="5232c-108">As just stated, this scenario is simplified for purposes of illustration.</span></span> <span data-ttu-id="5232c-109">请考虑消息传送应用程序，如图所示的一个示例。</span><span class="sxs-lookup"><span data-stu-id="5232c-109">Consider a sample messaging application such as the one illustrated below.</span></span> <span data-ttu-id="5232c-110">让我们假定，正常功能的行为，此应用程序是 BizTalk 接收通过文件的 XML 文件接收位置，然后将它发送到基于订阅的相应订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="5232c-110">Let’s assume that normal functional behavior for this application is that BizTalk receives an XML file via a file receive location, it then sends it to an appropriate subscriber based on a subscription.</span></span> <span data-ttu-id="5232c-111">若要有效地验证此方案中很重要我们在测试中执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5232c-111">To validate this scenario effectively it is important that we perform the following steps in the test:</span></span>  
  
1.  <span data-ttu-id="5232c-112">设置环境以确保其处于一致状态并准备好要运行测试：</span><span class="sxs-lookup"><span data-stu-id="5232c-112">Set up the environment to ensure that it is in a consistent state and ready for the test to be run:</span></span>  
  
    -   <span data-ttu-id="5232c-113">这可通过删除使用的两个文件位置中存在的任何文件。</span><span class="sxs-lookup"><span data-stu-id="5232c-113">This is done by deleting any files that are present in the two file locations used.</span></span>  
  
2.  <span data-ttu-id="5232c-114">运行测试来验证功能：</span><span class="sxs-lookup"><span data-stu-id="5232c-114">Run the test to verify functionality:</span></span>  
  
    -   <span data-ttu-id="5232c-115">创建 file 接收位置轮询的有效文件夹中 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="5232c-115">Create a valid XML message in the folder that the file receive location polls.</span></span>  
  
    -   <span data-ttu-id="5232c-116">验证正确的 XML 消息被置于出站文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="5232c-116">Validate that the correct XML message is placed in the outbound folder location.</span></span>  
  
    -   <span data-ttu-id="5232c-117">验证应涵盖的架构和消息的负载信息。</span><span class="sxs-lookup"><span data-stu-id="5232c-117">The validation should cover both the schema and the payload information for the message.</span></span> <span data-ttu-id="5232c-118">（通常几个键字段应进行检查。）</span><span class="sxs-lookup"><span data-stu-id="5232c-118">(Typically a couple of the key fields should be examined.)</span></span>  
  
3.  <span data-ttu-id="5232c-119">清除要确保环境处于相同的状态之前执行测试的环境：</span><span class="sxs-lookup"><span data-stu-id="5232c-119">Clean up the environment to ensure that the environment is in the same state as before the test executed:</span></span>  
  
    -   <span data-ttu-id="5232c-120">删除使用的两个文件位置中存在的任何文件。</span><span class="sxs-lookup"><span data-stu-id="5232c-120">Delete any files that are present in the two file locations used.</span></span>  
  
 <span data-ttu-id="5232c-121">![示例消息传送应用程序的 BizTalk](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span><span class="sxs-lookup"><span data-stu-id="5232c-121">![Sample BizTalk Messaging Application](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")</span></span>  
<span data-ttu-id="5232c-122">示例 BizTalk 消息传送应用程序</span><span class="sxs-lookup"><span data-stu-id="5232c-122">Sample BizTalk Messaging application</span></span>  
  
 <span data-ttu-id="5232c-123">每个测试用例开始和结束与测试用例 XML 标记中;测试名称参数传递给这此处所示。</span><span class="sxs-lookup"><span data-stu-id="5232c-123">Each test case begins and ends with the TestCase XML tag; the testName parameter is passed into this as indicated here.</span></span>  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 <span data-ttu-id="5232c-124">然后，我们输入 TestSetup 阶段中，在其中我们确保环境处于一致状态以运行测试。</span><span class="sxs-lookup"><span data-stu-id="5232c-124">Then we enter the TestSetup phase, in which we ensure that the environment is in a consistent state to run the test.</span></span> <span data-ttu-id="5232c-125">在此示例中，我们在我们 TestData 目录中删除任何包含的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="5232c-125">In this example, we delete any XML messages that are contained in our TestData directory.</span></span> <span data-ttu-id="5232c-126">这是使用**FileDeleteMultipleStep**。</span><span class="sxs-lookup"><span data-stu-id="5232c-126">This is done using the **FileDeleteMultipleStep**.</span></span>  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 <span data-ttu-id="5232c-127">然后输入什么是测试的测试执行阶段的最关键部分。</span><span class="sxs-lookup"><span data-stu-id="5232c-127">We then enter what is the most critical section of the test, the test execution stage.</span></span> <span data-ttu-id="5232c-128">此阶段可以包含多个测试步骤。</span><span class="sxs-lookup"><span data-stu-id="5232c-128">This stage can contain multiple test steps.</span></span> <span data-ttu-id="5232c-129">在此示例中我们使用 FileCreateStep 复制文档 (InDoc1.xml 可以看到在\<SourcePath > 标记) 为通过使用该文件放置我们接收位置。</span><span class="sxs-lookup"><span data-stu-id="5232c-129">In this example we use the FileCreateStep to copy a document (InDoc1.xml which can be seen in the \<SourcePath> tag) to a file drop which is used by our receive location.</span></span> <span data-ttu-id="5232c-130">务必要注意 BizUnit 支持用于在此步骤; 的文件名的唯一标识符这可以看到与 %creationpath 标记中的 Guid %引用。</span><span class="sxs-lookup"><span data-stu-id="5232c-130">It’s important to note that BizUnit supports using unique identifiers for filenames in this step; this can be seen with the %Guid% reference in the CreationPath tag.</span></span>  
  
 <span data-ttu-id="5232c-131">完成此操作后，我们需要使用**FileValidateStep**验证出站消息已创建。</span><span class="sxs-lookup"><span data-stu-id="5232c-131">After this has been completed, we need to use the **FileValidateStep** to validate the outbound message has been created.</span></span> <span data-ttu-id="5232c-132">你将注意到此步骤允许您指定超时值 （这是以毫秒为单位）、 目录和搜索模式。</span><span class="sxs-lookup"><span data-stu-id="5232c-132">You will notice this step allows you to specify a timeout value (this is in milliseconds), the directory and the search pattern.</span></span> <span data-ttu-id="5232c-133">除此之外， **DeleteFile**标记使您能够指定是否想要在已进行验证后删除的文件。</span><span class="sxs-lookup"><span data-stu-id="5232c-133">In addition to this, the **DeleteFile** tag enables you to specify whether you want the file to be removed after it has been validated.</span></span> <span data-ttu-id="5232c-134">最后，你还应注意验证涉及 XPath 查询，验证 XML 消息 （它会检查的值是 PONumber_0。） 中的 PONumber 节点检查和验证的任何出站消息是负载的另一个示例使用 BizUnit 时应遵循以下指导方针。</span><span class="sxs-lookup"><span data-stu-id="5232c-134">Finally, you should also note the validation includes an XPath query, which validates the PONumber node within the XML message (it checks that the value is PONumber_0.) Examination and validation of the payload of any outbound messages is another example of a guiding principle that you should follow when using BizUnit.</span></span>  
  
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
  
 <span data-ttu-id="5232c-135">测试用例的最后一个阶段是清理。</span><span class="sxs-lookup"><span data-stu-id="5232c-135">The final stage of the test case is the cleanup.</span></span> <span data-ttu-id="5232c-136">可以在这里，看到**文件**测试步骤用于清理由测试的目录。</span><span class="sxs-lookup"><span data-stu-id="5232c-136">As can be seen here, the **FileDelete** test step is used to clean up the directories used by the test.</span></span>  
  
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
  
 <span data-ttu-id="5232c-137">希望此示例演示如何在 BizUnit 中定义测试是相对比较简单，且，通过使用此测试框架，你将能够快速开发测试用例以提供您的应用程序的功能测试。</span><span class="sxs-lookup"><span data-stu-id="5232c-137">Hopefully this example illustrates that defining tests in BizUnit is relatively straightforward and that by using this test framework, you will be able to rapidly develop test cases to provide functional testing of your application.</span></span>  
  
### <a name="full-test-case-example"></a><span data-ttu-id="5232c-138">完整的测试用例示例</span><span class="sxs-lookup"><span data-stu-id="5232c-138">Full test case example</span></span>  
 <span data-ttu-id="5232c-139">完整的测试用例的配置文件内容此处提供了供你参考：</span><span class="sxs-lookup"><span data-stu-id="5232c-139">The full test case configuration file contents are included here for your reference:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5232c-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5232c-140">See Also</span></span>  
 [<span data-ttu-id="5232c-141">使用 BizUnit 以便于自动测试</span><span class="sxs-lookup"><span data-stu-id="5232c-141">Using BizUnit to Facilitate Automated Testing</span></span>](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)