---
title: 加载处理使用业务规则 （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: b8b878b782c49f1fc4827577444b8bffbec346fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380620"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a>贷款处理使用业务规则 （BizTalk Server 示例）
贷款处理使用业务规则的示例演示如何使用管理业务流程中的规则集以及如何使用的输入称为事实，组合来计算正在处理的文档中某些字段的设置。 事实可以是调用的结果。基于 NET 的程序集，从消息的 XML 中检索的值或从数据库检索到的数据。 此示例还演示如何更改这些规则在任何时候，会影响随后的计算，而无需重新部署。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示简化的贷款处理方案的上下文中的这些功能。 BizTalk Server 业务流程提取并处理的贷款申请，也称为贷款案例，XML 消息格式。 此业务流程使用业务规则引擎评估传入消息根据规则，修改结果的规则，该应用程序的消息，然后将消息写入一个文件作为输出文件夹。  

 基于多个源，包括正在处理的消息的事实此示例设置**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，并且**ResidencyStatus**正在处理的消息的元素。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Business Rules\Loans 处理使用业务 Rules\  

 下表显示了本示例中的文件及其用途说明：  


|                                                                                    文件                                                                                    |                                                                                                                Description                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                   Case.xsd                                                                                    |                                                                                 对于入站的贷款应用程序，也称为贷款案例的架构文件。                                                                                  |
|                                                                                  Cleanup.bat                                                                                  |                   用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。                   |
|                                                                           Create_CustInfo_Table.sql                                                                           |                                                                              在 SQL Northwind 示例数据库中创建 CustInfo 表的 SQL 脚本。                                                                              |
|                                                                           LoanProcessorBinding.xml                                                                            |                                                                                               用于如端口绑定之类的自动化设置。                                                                                               |
|                                                                   LoansProcessor.btproj, LoansProcessor.sln                                                                   |                                                                                            此示例的 BizTalk 项目和解决方案文件。                                                                                             |
|                                                                             我的示例 Service.odx                                                                             |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此示例的业务流程。                                                              |
|                                                                                sampleLoan.xml                                                                                 |                                                               示例输入的文件，与在文件中的 XML 结构末尾的四个状态元素的空值。                                                               |
|                                                                                   Setup.bat                                                                                   |                                                                                                 用于生成和初始化本示例。                                                                                                  |
|         在 \CreateRules 文件夹中：<br /><br /> App.ico、 AssemblyInfo.cs、 Case.xsd、 CreateLoanProcessingPolicy.csproj、 CreateLoanProcessingPolicy.sln、 WriteToBRL.cs          | Visual C# 项目、 解决方案、 源和用于创建以编程方式创建的规则，在集中的应用程序的相关的文件。 有关以编程方式构建的规则集的示例，请参阅源文件 WriteToBRL.cs。 |
| 在 \myFactRetriever 文件夹中：<br /><br /> AssemblyInfo.cs<br /><br /> FactRetrieverForLoansProcessing.cs<br /><br /> myFactRetriever.csproj<br /><br /> myFactRetriever.sln |                 Visual C# 项目、 解决方案、 源和相关的文件，用于创建使用从先前添加到 Northwind 示例 SQL Server 数据库的 CustInfo 表检索信息的程序集。                  |

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a>若要生成并初始化贷款处理使用业务规则示例  

1. 请确保你的计算机上具有 Northwind 数据库。  

   > [!IMPORTANT]
   >  若要运行此示例，必须具有 Northwind SQL Server 示例数据库。 [下载](https://www.microsoft.com/download/details.aspx?id=23654)，并安装。 

2. 在命令窗口中，导航到以下文件夹：  

    \<*示例路径*\>\Business Rules\Loans 处理使用业务规则  

3. 运行文件 Setup.bat，以执行以下操作：  

   - 清理 GAC 以消除之前运行此示例中的任何剩余数据。  

   - 编译并部署事实检索器程序 myFactRetreiever.dll。  

   - 使用 SQL 脚本文件 Create_CustInfo_Table.sql，将添加到 Northwind 示例 SQL 数据库名为 CustInfo 的表。  

   - 清理共享 SQL 规则存储以消除之前运行此示例的剩余部分。  

   - 创建、 发布，并部署贷款处理规则集的最新版本 (1.0)。  

     > [!NOTE]
     >  可以使用业务规则编辑器工具提供与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]检查以编程方式设置的规则。  

   - 创建输入 (In) 和输出 (Out) 文件夹对于此示例。  

   - 编译并部署剩余[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]对于此示例，其中包括包含用于协调本示例的业务流程的 BizTalk 项目的项目。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  

     > [!NOTE]
     >  此示例将显示以下警告时创建并绑定端口：  
     >   
     >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
     >   
     >  您可以放心地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用该接收位置，并启动发送端口。  

   - 登记并启动业务流程。  

> [!NOTE]
>  如果你的 BizTalk 主机名不是 BizTalkServerApplication，修改的文件 Setup.bat 文件和 LoanProcessorBinding.xml 以反映正确的主机名。  
> 
> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
> 
> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
> 
> [!NOTE]
>  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="running-this-sample"></a>运行本示例  

#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a>若要运行的贷款处理使用业务规则示例  

1. 到文件 sampleLoan.xml 的副本粘贴**\In**文件夹。  

2. 查看文件夹中创建的.xml 文件**出**。它包含输入的 XML 消息添加到以下四个状态元素的 XML 结构末尾的数据：**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，并且**ResidencyStatus**。  

   可以使用业务规则编辑器工具更改规则集中规则并重新部署这些规则。  

#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a>若要使用业务规则编辑器工具更改一个或多个规则组中的规则  

1. 单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。  

   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  

2. 在中**SQL Server**对话框中，单击**确定**连接到规则存储。  

3. 在**策略浏览器**，节点的下级**LoanProcessing**，右键单击**版本 1.0 – 已部署**节点，并单击**复制**。  

4. 右键单击**LoanProcessing**，然后单击**粘贴**。  

5. 更改任何规则或操作将导致不同的值的方式**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**元素。 确保也更改的值求反运算部分 (实质上， **Else**子句) 选择要更改任何规则。  

    下表显示了此示例使用的规则集。 除非明确提及，否则事实是从传入的 XML 消息。 字符串 (db) 表示数据库作为事实的源。  


   |  规则编号   |        规则名称        |                                                                             Description                                                                             |
   |----------------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       1        |   收入状态规则    |                                       IF **BasicSalary** + **OtherIncome** > 0<br /><br /> 然后**IncomeStatus** = **有效**                                        |
   |       2        | 承诺状态规则 | 如果**ID** == **ID (db)**<br /><br /> 和<br /><br /> IF **CreditCardBalance (db)** > 500<br /><br /> 然后**CommitmentsStatus** =<br /><br /> "计算承诺" |
   |       3        | 就业状态规则  |                                  如果**EmploymentType &#124; TimeInMonths** > 18<br /><br /> 然后**EmploymentStatus** = **有效**                                   |
   |       4        |  Residency Status Rule  |                                  IF **PlaceOfResidence &#124; TimeInMonths** > 18<br /><br /> 然后**ResidencyStatus** = **有效**                                  |
   | !1, !2, !3, !4 |     求反运算规则      |    条件的逻辑**不**规则 1 – 4 中所述相应条件。 引发的操作是更改正在设置的字符串。     |


6. 右键单击**版本 1.1 （未保存）** 节点，并单击**保存**。  

7. 右键单击**1.1 版**节点，并单击**发布**。  

8. 右键单击**1.1 版**节点，并单击**部署**。  

9. 等待 60 秒以使更改传播到共享 SQL Server 规则存储。  

10. 将文件 sampleLoan.xml 的副本粘贴到文件夹**在**。  

11. 查看文件夹中创建的.xml 文件**出**。它包含输入的 XML 消息添加到以下四个状态元素的 XML 结构末尾的数据：**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，并且**ResidencyStatus**。 添加到这些元素的数据将可能不同，从上一个运行，基于此过程的步骤 5 中所做的更改的性质。  

## <a name="comments"></a>注释  
 如果你想要查看此示例的跟踪信息，必须取消部署和使用业务规则引擎部署向导，然后重新部署相关规则集 （贷款处理）。  

 此示例演示如何使用业务规则应用形式的业务流程内规则的业务策略。 它还演示了如何更改策略，并在业务流程内动态反映而无需重新编译或重新部署业务流程解决方案在策略中已更改。  

 输入的贷款案例为此示例是具有以下结构的 XML 消息：  

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

## <a name="see-also"></a>请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)