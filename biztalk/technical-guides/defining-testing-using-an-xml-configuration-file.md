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
# <a name="defining-testing-using-an-xml-configuration-file"></a>定义测试使用 XML 配置文件
BizUnit 提供两种方法来定义测试： 通过 XML 配置文件和 Excel 工作表。 本主题重点介绍使用 XML 配置文件以定义测试;但是，您还应注意 BizUnit SDK，因为它提供了如何定义 BizUnit 测试用例使用 Excel 的一个有趣示例。 此外，您可能希望调查 BizUnit 设计器工具，它提供用于快速创建 BizUnit 测试用例的 GUI。 本主题概述了如何定义测试用例使用 XML 配置使用非常简化的方案。  
  
## <a name="overview-of-defining-a-bizunit-test-case-using-xml-configuration"></a>定义使用 XML 配置 BizUnit 测试用例的概述  
 如只是所述，简化了这种情况下，为便于说明。 请考虑消息传送应用程序，例如如下图所示的一个示例。 让我们认为正常功能行为，此应用程序是 BizTalk 接收 XML 文件通过文件接收位置，然后将它发送到基于订阅的相应订阅服务器。 若要有效地验证此方案中很重要我们在测试中执行以下步骤：  
  
1. 设置环境以确保其处于一致状态并准备好运行测试的：  
  
   -   这是通过删除使用的两个文件位置中存在的任何文件。  
  
2. 运行测试以验证功能：  
  
   -   创建文件接收位置轮询一个有效的文件夹中 XML 消息。  
  
   -   验证正确的 XML 消息被置于出站文件夹位置。  
  
   -   验证应涵盖的架构和消息的有效负载信息。 （通常几个键字段应进行检查。）  
  
3. 清理环境以确保在环境处于相同状态之前执行的测试：  
  
   -   删除使用的两个文件位置中存在的任何文件。  
  
   ![示例 BizTalk 消息传送应用程序](../technical-guides/media/440fa6d7-d3a0-476f-9484-fbea77d87e40.gif "440fa6d7-d3a0-476f-9484-fbea77d87e40")  
   示例 BizTalk 消息传送应用程序  
  
   每个测试用例开头和结尾的测试用例 XML 标记;测试名称参数将传递到这，此处所示。  
  
```  
<TestCase testName="Test_01_FILECopyWithXmlValidation">  
```  
  
 然后，输入 TestSetup 阶段，在其中我们确保在环境处于一致状态以运行测试。 在此示例中，我们 TestData 目录中删除任何包含的 XML 消息。 这是使用**FileDeleteMultipleStep**。  
  
```  
<TestSetup>  
   <TestStep assemblyPath="" typeName="Microsoft.Services.BizTalkApplicationFramework.BizUnit.FileDeleteMultipleStep">  
      <Directory>..\..\..\TestData\</Directory>  
         <SearchPattern>*.xml</SearchPattern>   
      </TestStep>  
</TestSetup>  
```  
  
 然后输入什么是测试，测试执行阶段的最关键部分。 此阶段可以包含多个测试步骤。 在此示例中我们使用 FileCreateStep 复制文档 (所示的 InDoc1.xml \<SourcePath\>标记) 使用该文件放到我们接收位置。 务必要注意的是 BizUnit 支持使用在此步骤; 文件名唯一标识符这可以看到与 %creationpath 标记中的 Guid %引用。  
  
 此操作完成后后，我们需要使用**FileValidateStep**若要验证出站消息已创建。 您将注意到此步骤允许您指定超时值 （这是以毫秒为单位）、 目录和搜索模式。 除此之外， **DeleteFile**标记可用于指定是否想要删除已验证的文件。 最后，您还应注意验证包括 XPath 查询，验证 XML 消息 （它检查的值是 PONumber_0。） 中的 PONumber 节点检查和验证的任何出站消息的有效负载是使用 BizUnit 时应遵循的指导原则的另一个示例。  
  
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
  
 测试用例的最后一个阶段是清理。 在这里，可以看出**FileDelete**测试步骤用于清理测试所使用的目录。  
  
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
  
 希望此示例说明在 BizUnit 中定义的测试的相对来说比较简单，并且，通过使用此测试框架，您将能够快速开发提供你的应用程序的功能测试的测试用例。  
  
### <a name="full-test-case-example"></a>完整的测试用例示例  
 完整的测试用例的配置文件内容包含了供你参考：  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用 BizUnit 优化自动测试](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)