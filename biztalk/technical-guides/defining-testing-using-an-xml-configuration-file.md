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
# <a name="defining-testing-using-an-xml-configuration-file"></a>定义测试使用 XML 配置文件
BizUnit 提供两种方法来定义测试： 通过 XML 配置文件和通过 Excel 工作表。 本主题重点介绍使用 XML 配置文件来定义测试;但是，你还应注意 BizUnit SDK，因为它提供了如何定义使用 Excel BizUnit 测试用例的一个有趣示例。 此外，你可能希望调查 BizUnit 设计器工具，它提供一个 GUI，允许快速创建 BizUnit 测试用例。 本主题概述了如何定义使用 XML 配置使用非常简化的方案的测试用例。  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a>定义 BizUnit 测试用例使用 XML 配置概述  
 如只需所述，这种情况下得到了简化，演示目的。 请考虑消息传送应用程序，如图所示的一个示例。 让我们假定，正常功能的行为，此应用程序是 BizTalk 接收通过文件的 XML 文件接收位置，然后将它发送到基于订阅的相应订阅服务器。 若要有效地验证此方案中很重要我们在测试中执行以下步骤：  
  
1.  设置环境以确保其处于一致状态并准备好要运行测试：  
  
    -   这可通过删除使用的两个文件位置中存在的任何文件。  
  
2.  运行测试来验证功能：  
  
    -   创建 file 接收位置轮询的有效文件夹中 XML 消息。  
  
    -   验证正确的 XML 消息被置于出站文件夹位置。  
  
    -   验证应涵盖的架构和消息的负载信息。 （通常几个键字段应进行检查。）  
  
3.  清除要确保环境处于相同的状态之前执行测试的环境：  
  
    -   删除使用的两个文件位置中存在的任何文件。  
  
 ![示例消息传送应用程序的 BizTalk](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")  
示例 BizTalk 消息传送应用程序  
  
 每个测试用例开始和结束与测试用例 XML 标记中;测试名称参数传递给这此处所示。  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 然后，我们输入 TestSetup 阶段中，在其中我们确保环境处于一致状态以运行测试。 在此示例中，我们在我们 TestData 目录中删除任何包含的 XML 消息。 这是使用**FileDeleteMultipleStep**。  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 然后输入什么是测试的测试执行阶段的最关键部分。 此阶段可以包含多个测试步骤。 在此示例中我们使用 FileCreateStep 复制文档 (InDoc1.xml 可以看到在\<SourcePath > 标记) 为通过使用该文件放置我们接收位置。 务必要注意 BizUnit 支持用于在此步骤; 的文件名的唯一标识符这可以看到与 %creationpath 标记中的 Guid %引用。  
  
 完成此操作后，我们需要使用**FileValidateStep**验证出站消息已创建。 你将注意到此步骤允许您指定超时值 （这是以毫秒为单位）、 目录和搜索模式。 除此之外， **DeleteFile**标记使您能够指定是否想要在已进行验证后删除的文件。 最后，你还应注意验证涉及 XPath 查询，验证 XML 消息 （它会检查的值是 PONumber_0。） 中的 PONumber 节点检查和验证的任何出站消息是负载的另一个示例使用 BizUnit 时应遵循以下指导方针。  
  
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
  
 测试用例的最后一个阶段是清理。 可以在这里，看到**文件**测试步骤用于清理由测试的目录。  
  
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
  
 希望此示例演示如何在 BizUnit 中定义测试是相对比较简单，且，通过使用此测试框架，你将能够快速开发测试用例以提供您的应用程序的功能测试。  
  
### <a name="full-test-case-example"></a>完整的测试用例示例  
 完整的测试用例的配置文件内容此处提供了供你参考：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用 BizUnit 以便于自动测试](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)