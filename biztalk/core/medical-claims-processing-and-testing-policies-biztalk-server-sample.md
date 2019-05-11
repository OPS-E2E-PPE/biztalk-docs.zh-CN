---
title: 医疗索赔处理和测试保单 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5108e5d26b7da7761285c8b8e7ec1bde8deaf00c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325553"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a>医疗索赔处理和测试保单 （BizTalk Server 示例）
医疗索赔处理和测试保单示例演示如何创建规则集包含多个规则检查派生自数据库表和入站的文档的事实，并使用。基于网络的对象记录索赔处理结果。  
  
 此示例演示使用一个简单的声明处理方案的完整执行。基于 NET 的应用程序使用业务规则引擎来运行医疗声明规则集对传入声明来确定报销申请的状态和状态的原因。  
  
> [!NOTE]
>  此示例还演示如何跟踪业务规则引擎执行使用调试跟踪文件。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例适用于已提交的声明规则按以下顺序：  
  
1.  如果声明的总金额超过策略允许的最大，拒绝声明。  
  
2.  如果客户端具有仍保留在医院比策略允许的最大的多个夜晚将拒绝该声明。  
  
3.  如果在声明上的日期在将来，会拒绝声明。  
  
4.  如果策略不是有效，则会拒绝该声明。  
  
5.  如果策略已过期，请将潜在顾客发送到销售部门的策略 ID 和客户名称。  
  
6.  否则，将批准该声明。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Business Rules\Medical 声明 Processing and Testing Policies\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Create_PolicyValidity_Table.sql|添加一个新表的 SQL 脚本名 PolicyValidity 为到 Northwind 示例数据库。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \Claims 文件夹中：<br /><br /> AssemblyInfo.cs、 Claims.csproj，Claims.sln Claims.cs|项目、 解决方案、 源和相关的文件，此示例中，记录索赔处理结果的部分称为**然后**规则的部分。|  
|在 \FactRetrieverForClaimsProcessing 文件夹中：<br /><br /> AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln|项目、 解决方案、 源和相关的文件，此示例中，提供从创建此示例的 PolicyValidity 表中检索信息的长期事实检索器的部分。|  
|\RulesForMedicalClaims 文件夹的位置：<br /><br /> App.ico、 AssemblyInfo.cs、 RulesForMedicalClaims.cs、 RulesForMedicalClaims.csproj、 RulesForMedicalClaims.sln|项目、 解决方案、 源和相关的文件，此示例中，以编程方式构成本示例 (RulesForMedicalClaims.exe) 和其中的主要可执行文件的部分定义和存储的规则集、 构造示例事实，然后运行使用设置的规则**PolicyTester**对象。|  
|\RulesForMedicalClaims 文件夹的位置：<br /><br /> MedicalClaims.xsd|此示例中定义的提交示例医疗索赔的结构的架构文件。|  
|\RulesForMedicalClaims 文件夹的位置：<br /><br /> sampleClaim.xml|符合 MedicalClaims.xsd 在文件中定义的架构的示例输入的文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a>若要生成并初始化医疗索赔处理和测试保单示例  
  
1. 请确保你的计算机上具有 Northwind 数据库。  
  
   > [!IMPORTANT]
   >  若要运行此示例，必须具有 Northwind SQL Server 示例数据库。 [下载](https://www.microsoft.com/download/details.aspx?id=23654)，并安装。 
  
2. 在命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Business Rules\Medical 声明 Processing and Testing Policies\  
  
3. 运行文件 Setup.bat，以执行以下操作：  
  
   - 编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目类型提供的此示例中，包括 Claims.dll、 FactRetrieverForClaimsProcessing.dll 和 RulesForMedicalClaims.dll。  
  
   > [!NOTE]
   >  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
   > 
   > [!NOTE]
   >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
  
   - 运行提供的 SQL 脚本 Create_PolicyValidity_Table.sql 使用 SQL 查询分析器。 该脚本创建表，PolicyValidity，与 Northwind 示例数据库中的两个示例行。 此表包含两列：ID 和 PolicyStatus。  
  
   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送和接收端口。  
  
   - 启用该接收位置，并启动发送端口。  
  
   - 登记并启动业务流程。  
  
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a>若要运行医疗索赔处理和测试保单示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Business Rules\Medical 索赔处理和测试 Policies\RulesForMedicalClaims\bin\Debug\  
  
2. 在命令行上运行文件 RulesForMedicalClaims.exe。  
  
   > [!NOTE]
   >  可以更改的示例声明文件 sampleClaim.xml 中各个元素的值，并重复运行该示例。 在这些元素中的不同值的预期的输出所示后面的列表。  
  
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
  
-   声明其日期不是有效 (日期 > 当前日期)，则以下输出中获取：  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   对于不是有效的策略 ID 的声明 (例如，通过更改**ID**元素具有值为 2) 由于策略过期，获得以下输出：  
  
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
    >  文本文件、 outputtrace.txt，每次运行此示例文件夹...\RulesForMedicalClaims\bin\Debug 文件夹中创建。 它包含的规则执行调试跟踪和创建后下文件夹 \RulesForMedicalClaims\bin\Debug 每次执行循环。 可以检查该文件，请参阅输出跟踪规则执行。  
  
## <a name="comments"></a>注释  
 将规则集计算中使用的事实源是：  
  
- 长期事实检索器。实现的基于网络的应用程序**IFactReriever**接口中，生成 FactRetrieverForClaimsProcessing 文件夹中。 它使用医疗索赔处理策略从 PolicyValidity 数据库检索数据 （在数据集的形式） 并在规则条件计算中使用。  
  
- 声明是包含以下信息，存储在同级元素的 XML 文档的形式：名称、 ID、 数量、 夜晚和日期。  
  
- 答:。基于 NET 的类库 （声明），与**ClaimResults**类用于记录状态以及使用属性、 声明的原因并发送一个潜在顾客 （如果该策略不是有效的） 通过调用**SendLeads**使用 ID 和名称作为参数的方法。  
  
  基于这些事实源，可以非正式地描述为这种情况下，如下所示定义的规则：  
  
1. 检查传入声明是否有效。 如果量高于允许限制声明，如果策略已过期 （已通过检查数据库表验证） 的夜晚数是否超过了最大允许的限制，并为将来日期作出声明，声明无效。 如果已确定该声明不是有效，适当地设置的状态和原因的声明。  
  
2. 如果传入声明的策略 ID 已过期，请向策略续订部门发送 （与策略 ID 和客户名称）。  
  
3. 如果声明是有效的相应地设置的状态和原因的声明。  
  
   规则和及其术语绑定的更正式表示形式如下所示：  
  
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
  
-   **规则 2。在医院中所用的夜晚，**  
  
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
  
-   **规则 4。策略有效期**  
  
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
  
## <a name="see-also"></a>请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)