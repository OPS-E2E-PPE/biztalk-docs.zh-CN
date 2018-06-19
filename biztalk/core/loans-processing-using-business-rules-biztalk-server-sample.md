---
title: 借处理使用业务规则 （BizTalk Server 示例） |Microsoft 文档
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
ms.assetid: 3e1c80c6-adc1-4a0f-83fd-409ce1b8f21f
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82476c440f1bae482eff5308f1a5238f8bd85d92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008342"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a>贷款处理使用业务规则 （BizTalk Server 示例）
使用业务规则的贷款处理示例说明如何使用在业务流程中管理的规则集，以及如何使用输入组合（称为事实）来计算正在处理的文档中某些字段的设置。 事实可以是调用基于 .NET 的程序集的结果、从 XML 格式的消息中检索的值或从数据库检索的数据。 本示例还说明如何随时更改规则以便影响随后的计算，而无需重新部署。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例将在简化的贷款处理方案的上下文中说明这些功能。 BizTalk Server 业务流程提取并处理 XML 消息格式的贷款申请（也称为贷款案例）。 此业务流程将使用业务规则引擎根据规则评估传入消息，并利用规则申请结果修改消息，然后将消息以文件的形式写入输出文件夹。  
  
 基于事实从多个源，包括消息处理，此示例会将设置**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**正在处理的消息的元素。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Business Rules\Loans 处理使用业务 Rules\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Case.xsd|入站贷款申请（也称为贷款案例）的架构文件。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Create_CustInfo_Table.sql|SQL 脚本，用于在 SQL Northwind 示例数据库中创建 CustInfo 表。|  
|LoanProcessorBinding.xml|用于如端口绑定之类的自动化设置。|  
|LoansProcessor.btproj、LoansProcessor.sln|本示例的 BizTalk 项目和解决方案文件。|  
|My Sample Service.odx|本示例的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。|  
|sampleLoan.xml|示例输入文件，文件中 XML 结构末尾的四个状态元素的值为空。|  
|Setup.bat|用于生成和初始化本示例。|  
|\CreateRules 文件夹中：<br /><br /> App.ico、AssemblyInfo.cs、Case.xsd、CreateLoanProcessingPolicy.csproj、CreateLoanProcessingPolicy.sln、WriteToBRL.cs|用于创建应用程序的 Visual C# 项目、解决方案、源和相关文件，该应用程序将以编程方式创建规则集中的规则。 有关以编程方式生成规则集的示例，请参阅源文件 WriteToBRL.cs。|  
|\myFactRetriever 文件夹中：<br /><br /> AssemblyInfo.cs<br /><br /> FactRetrieverForLoansProcessing.cs<br /><br /> myFactRetriever.csproj<br /><br /> myFactRetriever.sln|用于创建程序集的 Visual C# 项目、解决方案、源和相关文件，该程序集用于从先前添加到 Northwind 示例 SQL Server 数据库的 CustInfo 表检索信息。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a>生成并初始化使用业务规则的贷款处理示例  
  
1.  确保您的计算机上具有 Northwind 数据库。  
  
    > [!IMPORTANT]
    >  若要运行此示例，你必须有 Northwind SQL Server 示例数据库。 [下载](https://www.microsoft.com/download/details.aspx?id=23654)，并安装。 
  
2.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Business Rules\Loans 处理使用业务规则  
  
3.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   清理 GAC 以消除之前运行此示例所残留的任何数据。  
  
    -   编译并部署事实检索器程序 myFactRetreiever.dll。  
  
    -   使用 SQL 脚本文件 Create_CustInfo_Table.sql，将名为 CustInfo 的表添加到 Northwind 示例 SQL 数据库中。  
  
    -   清理共享 SQL 规则存储以消除之前运行此示例所残留的数据。  
  
    -   创建、发布并部署贷款处理规则集的最新版本 (1.0)。  
  
        > [!NOTE]
        >  可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的业务规则编辑器工具检查以编程方式设置的规则。  
  
    -   为本示例创建输入 (In) 和输出 (Out) 文件夹。  
  
    -   编译并部署本示例的其余 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，包括 BizTalk 项目，该项目包含用于协调本示例的业务流程。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
        > [!NOTE]
        >  本示例在创建和绑定端口时将显示以下警告：  
        >   
        >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
        >   
        >  可以安全地忽略这些警告。 （考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）  
  
    -   启用接收位置并启动发送端口。  
  
    -   登记并启动业务流程。  
  
> [!NOTE]
>  如果 BizTalk 主机名不是 BizTalkServerApplication，请修改 Setup.bat 文件和 LoanProcessorBinding.xml 文件以反映正确的主机名。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集签名。  
  
> [!NOTE]
>  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a>运行使用业务规则的贷款处理示例  
  
1.  粘贴到文件 sampleLoan.xml 一份**\In**文件夹。  
  
2.  观察的文件夹中创建的.xml 文件**出**。输入的 XML 消息包含添加到以下四个状态元素末尾的 XML 结构的数据： **IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**。  
  
 可以使用业务规则编辑器工具更改规则集中的规则，然后重新部署这些规则。  
  
#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a>使用业务规则编辑器工具更改规则集中一个或多个规则  
  
1.  单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在**SQL Server**对话框中，单击**确定**以连接到规则存储。  
  
3.  在**策略资源管理器**，节点下**LoanProcessing**，右键单击**版本 1.0 – 部署**节点，，然后单击**复制**。  
  
4.  右键单击**LoanProcessing**，然后单击**粘贴**。  
  
5.  更改任何规则或操作将导致不同的值的方式**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**元素。 确保你还更改求反部分的值 (实质上， **Else**子句) 选择要更改任何规则。  
  
     下表显示了本示例使用的规则集。 除非明确提及，否则事实来自传入的 XML 消息。 字符串 (db) 表示数据库作为事实的源。  
  
    |规则编号|规则名称|Description|  
    |-----------------|---------------|-----------------|  
    |1|Income Status Rule|如果**BasicSalary** + **OtherIncome** > 0<br /><br /> 然后**IncomeStatus** = **有效**|  
    |2|Commitments Status Rule|如果**ID** == **ID (db)**<br /><br /> 和<br /><br /> 如果**CreditCardBalance (db)** > 500<br /><br /> 然后**CommitmentsStatus** =<br /><br /> "Compute Commitments"|  
    |3|Employment Status Rule|如果**EmploymentType &#124;TimeInMonths** > 18<br /><br /> 然后**EmploymentStatus** = **有效**|  
    |4|Residency Status Rule|如果**PlaceOfResidence &#124;TimeInMonths** > 18<br /><br /> 然后**ResidencyStatus** = **有效**|  
    |!1, !2, !3, !4|Negation Rules|条件逻辑**不**规则 1-4 中所述的相应条件。 生成操作是设置的字符串中的更改。|  
  
6.  右键单击 **（不保存） 1.1 版**节点，，然后单击**保存**。  
  
7.  右键单击**版本 1.1**节点，，然后单击**发布**。  
  
8.  右键单击**版本 1.1**节点，，然后单击**部署**。  
  
9. 等待 60 秒以使更改传播到共享 SQL Server 规则存储。  
  
10. 将文件 sampleLoan.xml 的副本粘贴到文件夹**中**。  
  
11. 观察的文件夹中创建的.xml 文件**出**。输入的 XML 消息包含添加到以下四个状态元素末尾的 XML 结构的数据： **IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**。 根据此过程步骤 5 中所做更改的性质，添加到这些元素的数据与以前的运行可能不同。  
  
## <a name="comments"></a>注释  
 如果希望查看本示例的跟踪信息，您必须取消部署相关规则集（贷款处理），然后使用业务规则引擎部署向导重新部署。  
  
 本示例说明如何使用业务规则以业务流程内规则的形式应用业务策略。 它还说明如何更改策略，以及如何使策略中的更改动态反映在业务流程内，而不必重新编译或重新部署业务流程解决方案。  
  
 本示例的输入贷款案例为具有以下结构的 XML 消息：  
  
```  
    Name  
    ID  
    Income  
        BasicSalary  
        OtherIncome  
    EmploymentType  
        TimeInMonths  
    PlaceOfResidence  
        TimeInMonths  
    CommitmentsStatus  
    IncomeStatus  
    EmploymentStatus  
    ResidencyStatus  
```  
  
## <a name="see-also"></a>另请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)