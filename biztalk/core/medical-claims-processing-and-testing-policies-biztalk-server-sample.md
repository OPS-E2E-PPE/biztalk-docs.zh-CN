---
title: "医疗声明处理和测试策略 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33c8921e037b9f9628c0e0ee97a915f62ab634ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a>医疗声明处理和测试策略 （BizTalk Server 示例）
“医疗索赔处理和测试保单”示例演示如何创建包含多个规则的规则集，这些规则检查从数据库表和入站文档推断得出的事实，并使用基于 .NET 的对象记录索赔处理结果。  
  
 此示例演示如何使用一个简单的声明处理方案端执行。基于网络的应用程序使用业务规则引擎运行医疗声明规则集对传入声明，以确定声明的状态和状态的原因。  
  
> [!NOTE]
>  此示例还演示如何使用调试跟踪文件的业务规则引擎执行跟踪。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例适用于已提交的声明规则的以下序列：  
  
1.  如果声明的总金额超过策略允许的最大，拒绝声明。  
  
2.  如果客户端段中已在医院比策略允许的最大的多个晚上将拒绝声明。  
  
3.  如果声明的日期是在将来将拒绝声明。  
  
4.  拒绝声明，如果该策略无效。  
  
5.  如果策略已过期，请将一个主管发送到策略 ID 和客户名称的销售部门。  
  
6.  否则，批准声明。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*> \Business Rules\Medical 声明处理和测试 Policies\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Create_PolicyValidity_Table.sql|添加一个新表的 SQL 脚本名 PolicyValidity 为包含到 Northwind 示例数据库。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \Claims 文件夹中：<br /><br /> AssemblyInfo.cs、 Claims.csproj，Claims.sln Claims.cs|项目、 解决方案、 源和相关的文件记录结果的处理，声明此示例的部分调用**然后**规则部分。|  
|在 \FactRetrieverForClaimsProcessing 文件夹中：<br /><br /> AssemblyInfo.cs、 FactRetrieverForClaimsProcessing.cs，FactRetrieverForClaimsProcessing.csproj FactRetrieverForClaimsProcessing.sln|项目、 解决方案、 源和相关的文件提供了从创建此示例的 PolicyValidity 表中检索信息的长期事实检索此示例的部分。|  
|\RulesForMedicalClaims 文件夹的内容：<br /><br /> App.ico、 AssemblyInfo.cs、 RulesForMedicalClaims.cs、 RulesForMedicalClaims.csproj、 RulesForMedicalClaims.sln|项目、 解决方案、 源和相关的文件，此示例以编程方式可以是此示例 (RulesForMedicalClaims.exe)，和的主可执行文件的部分定义也将规则集，构造示例事实，然后运行规则集使用**PolicyTester**对象。|  
|\RulesForMedicalClaims 文件夹的内容：<br /><br /> MedicalClaims.xsd|于此示例中定义的提交示例医疗声明的结构的架构文件。|  
|\RulesForMedicalClaims 文件夹的内容：<br /><br /> sampleClaim.xml|示例符合架构文件 MedicalClaims.xsd 中定义的输入的文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a>生成并初始化“医疗索赔处理和测试保单”示例  
  
1.  确保您的计算机上具有 Northwind 数据库。  
  
    > [!IMPORTANT]
    >  为了运行本示例，您必须拥有名为 Northwind 的数据库。 [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] 和 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 不提供 Northwind 示例数据库。 若要创建 Northwind 数据库，下载安装文件从[http://go.microsoft.com/fwlink/?LinkId=196020](http://go.microsoft.com/fwlink/?LinkId=196020)，并按照说明操作。  
  
2.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \Business Rules\Medical 声明处理和测试 Policies\  
  
3.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   为本示例编译并部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，包括 Claims.dll、FactRetrieverForClaimsProcessing.dll 和 RulesForMedicalClaims.dll。  
  
    > [!NOTE]
    >  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
    > [!NOTE]
    >  如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集签名。  
  
    -   运行提供的 SQL 脚本 Create_PolicyValidity_Table.sql 使用 SQL 查询分析器中。 由脚本创建的表，PolicyValidity，Northwind 示例数据库中的两个示例行。 此表包含两列： ID 和 PolicyStatus。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。  
  
    -   启用接收位置并启动发送端口。  
  
    -   登记，并启动业务流程。  
  
    > [!NOTE]
    >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a>运行“医疗索赔处理和测试保单”示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \Business Rules\Medical 声明处理和测试 Policies\RulesForMedicalClaims\bin\Debug\  
  
2.  在命令行上运行文件 RulesForMedicalClaims.exe。  
  
    > [!NOTE]
    >  你可以更改的示例声明文件 sampleClaim.xml 中各个元素的值和重复运行示例。 这些元素中的不同值的预期的输出所示后面的列表。  
  
 基于已提交的示例声明文件中的值的各种组合的输出方案是：  
  
-   声明其量超过 1000 美元，可获得以下输出：  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   夜晚其数目超过 10 声明，可获得以下输出：  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   声明其日期无效 (日期 > 当前日期)，则以下输出中获得：  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   不是有效的策略 ID 与声明 (例如，通过更改**ID**元素具有值为 2) 由于策略过期获得以下输出：  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   声明的有效，可获得以下输出：  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  文本文件、 outputtrace.txt，每次运行此示例文件夹...\RulesForMedicalClaims\bin\Debug 文件夹中创建。 它包含的规则执行调试跟踪，并创建它时每次执行周期下文件夹 \RulesForMedicalClaims\bin\Debug 后。 你可以检查该文件，请参阅规则执行的输出跟踪。  
  
## <a name="comments"></a>注释  
 在规则集计算中使用的事实来源是：  
  
-   长期的事实检索器。基于网络的应用程序实现**IFactReriever**接口，文件夹 FactRetrieverForClaimsProcessing 中生成。 它通过处理策略的医疗声明用于从 PolicyValidity 数据库中检索数据 （在数据集的形式） 并要在规则条件计算中使用。  
  
-   声明是包含以下信息，存储在同级元素的 XML 文档的形式： 名称、 ID、 金额、 晚上和日期。  
  
-   答:。基于网络的类库 （声明） 与**ClaimResults**类用于记录的状态和使用属性，声明的原因以及 （如果该策略不是有效的） 发送一个主管通过调用**SendLeads**具有 ID 和名称作为参数的方法。  
  
 基于这些事实源，你可以被不正式地描述为这种情况下，如下所示定义的规则：  
  
1.  检查传入声明有效。 如果量超过了允许的限制声明，如果策略已过期 （通过检查数据库表已验证），如果晚上数目超过了允许的最大限制，并且将来的日期进行声明，声明无效。 如果已确定声明不是有效，正确设置的状态和声明的原因。  
  
2.  如果传入声明的策略 ID 已过期，请向策略续订部门发送一个主管 （具有策略 ID 和客户名称）。  
  
3.  如果声明是有效的正确设置的状态和声明的原因。  
  
 更正式的表示形式和术语绑定规则如下所示：  
  
-   **规则 1。量检查**  
  
    ```  
    IF Amount in the XML document is > 1000  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"\  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **规则 2。晚上花在医院**  
  
    ```  
    IF number of nights in the XML document is > 10  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **规则 3。日期有效性**  
  
    ```  
    IF date on the incoming XML claim is > Today  
      AND   
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Cannot submit claims in the future!"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **规则 4。策略有效性**  
  
    ```  
    IF Policy is invalid for the ID in the XML claim (check database)  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Policy Invalid"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **规则 5。潜在销售顾客**  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   **规则 6。接受的声明**  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [业务规则 （BizTalk Server 示例文件夹中）](../core/business-rules-biztalk-server-samples-folder.md)