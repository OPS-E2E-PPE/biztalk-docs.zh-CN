---
title: 错误处理 （BizTalk Server 示例文件夹中） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, errors
- errors, examples
- examples, messages
- messages, examples
- messages, errors
ms.assetid: b39791ed-277b-4625-b9a9-72480a1b6ff6
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 386e9729ac32cb08863e2ac3e0699ecda7890dbc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971475"
---
# <a name="error-handling-biztalk-server-samples-folder"></a>错误处理（BizTalk Server 示例文件夹）
本示例的目的是为基于内容的路由 (CBR) 应用程序生成错误处理功能。  
  
## <a name="prerequisites"></a>先决条件  
 若要运行本示例，建议你安装 Microsoft Office InfoPath 2010 或更高版本。 你可以在不使用 InfoPath 的情况下运行本示例，但在这种情况下，你无法通过 HTTP 适配器查看费用报告以及费用报告的提交。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例可实现费用报告处理系统部分。 具体而言，本示例执行下列操作：  
  
1.  定义费用报告架构，该架构包含有关费用报告和单个提交者（包括部门名称）的信息。  
  
2.  使用 InfoPath 通过目录或 Web Services 提供费用报告的提交。  
  
3.  提升**部门**和**correlationID**消息中的属性文档，以便它可以用于端口筛选器中控制路由。  
  
4.  将属于 Marketing 部门的费用报告路由到目录中的某个文件，从而模拟送达该部门的后端系统。  
  
5.  对属于 Marketing 之外的部门的费用报告生成失败消息。 失败消息包括有关错误（包括错误代码和错误说明）的信息。  
  
6.  将失败消息路由给接收方人员（业务用户或应用程序操作员）以进行更正和重新提交。  
  
7.  如上所述，根据部门路由重新提交的费用报告。  
  
 大部分工作都是通过 BizTalk 业务流程调度完成的。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 设计依赖 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的默认发送和接收 XML 管道、属性升级、订阅筛选器和业务流程调度来路由消息。 下表列出了设计元素及其选入理由。  
  
|设计元素|选择的原因|  
|--------------------|--------------------------|  
|默认 XML 接收管道|-XMLReceive 管道支持属性提升;PassThruReceive 管道却没有。<br />-入站的消息已在 XML 格式，并且不需要基本反汇编和参与方解析之外的处理。|  
|针对失败消息的路由|接收端口挂起失败的消息和默认情况下生成否定确认。 启用路由后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会尝试将处理失败的所有消息路由到某个订阅应用程序（例如另一个接收端口或业务流程调度）。|  
|属性提升|-BizTalk Server 取决于要进行路由的属性字段。 业务流程使用可分辨字段，并且该字段不能用于路由。|  
|订阅筛选器|-订阅筛选器执行通过捕获满足基于属性的字段的一个或多个条件的消息路由。|  
|BizTalk 业务流程调度|-提供了机会将信息添加到失败的消息。<br />-启用路由的失败消息人工干预的专用位置。<br />-进程重新提交费用报表。|  
|XMLTransmit|-执行基本的传出的 XML 消息的程序集。 PassThruTransmit 管道不提供其他支持。|  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于 <`Samples Path>`\Messaging\ErrorHandling\\。  
  
 下表包含本示例的文件列表。  
  
|文件|Description|  
|----------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。<br /><br /> 删除发送和接收端口。<br /><br /> 根据需要删除 Internet 信息服务 (IIS) 虚拟目录。|  
|ErrorHandling.sln|本示例的 Visual Studio 解决方案文件。|  
|ErrorHandlingBinding.xml|本示例的绑定文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|Expense Report – John Doe.xml|示例费用报告 InfoPath 文档。|  
|Invalid Expense Report – John Doe.xml|示例费用报告 InfoPath 文档，其中包含无效的数据。|  
|在 ErrorHandler 文件夹中：<br /><br /> ErrorHandler.btproj|业务流程的 BizTalk 项目。|  
|在 ErrorHandler 文件夹中：<br /><br /> ResubmitLogic.odx|订阅失败消息，将失败消息发送给接收方人员进行更正，然后将更正后的消息重新提交回服务器进行路由的业务流程。|  
|在 ErrorHandler 文件夹中：<br /><br /> SuspendMessage.odx|用于挂起无法在错误处理业务流程中处理的消息的业务流程。|  
|在 InfoPathForms 文件夹中：<br /><br /> Expense Report.xsn<br /><br /> Expense Report - Resubmit.xsn|费用报告 InfoPath 表单以及用于查看和重新提交失败消息的表单。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> ExpenseReportSchema.xsd|费用报告文档的 XML 架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PipelinesAndSchemas.btproj|本示例的 BizTalk 项目。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PropertySchema.xsd|本示例的属性架构。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 本示例为创建自己的错误处理过程提供了一个起点。  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>生成并初始化 Compose 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     <`Samples Path`>**\Messaging\ErrorHandling**  
  
2.  运行**Setup.bat**，这将执行以下操作：  
  
    -   创建三个文件夹： **ExpenseReportIn**， **ExpenseReportOut**，和**ResubmittedReportIn**以下路径下：  
  
         <`Samples Path`>**\Messaging\ErrorHandling**  
  
    -   将复制并发布 InfoPath 窗体**支出 Report.xsn**和**费用报表 – Resubmit.xsn**到文件夹**C:\Temp\InfoPathForms**。  
  
    -   为本示例编译 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目。  
  
    -   创建一个名为的虚拟目录**ExpenseReports**。  
  
    -   创建新的 BizTalk 应用程序调用**错误处理示例**，并将部署到其中的示例程序集。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置以及发送和接收端口。  
  
    -   登记并启动业务流程，启用接收位置，然后启动发送端口。  
  
         如果选择在不运行 Setup.bat 的情况下打开并生成本示例中的项目，则必须首先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。 使用该密钥对可以对示例程序集进行签名。  
  
3.  在尝试运行本示例之前，请确认在生成或初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
    > [!NOTE]
    >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
4.  如果使用的是 Internet Information Services (IIS) 7.0，则需要执行其他配置步骤，从而调整与本示例使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收位置对应的虚拟目录设置。 通过执行以下操作配置 IIS：  
  
    1.  使用 IIS 7.0 管理器为 BizTalk Isolated Host Users 组创建新的应用程序池。  
  
    2.  将应用程序池配置为以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 独立主机用户的身份运行。 （如果你已为其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收位置配置应用程序池，则可以跳过此步骤。）  
  
    3.  配置虚拟目录**ExpenseReport**为了使用 HTTP 接收在上一步中创建的应用程序池。  
  
     如果 BTSHTTPReceive.dll ISAPI 扩展尚不具有 Web 服务器扩展，则可通过将其状态设置为“允许”创建和启用该扩展。 你可以在 IIS 7.0 中通过使用 IIS 管理控制台 (要么直接下**管理工具**，或者通过计算机管理控制台)，如下所示：  
  
    1.  展开**Internet Information Services Manager**树。  
  
    2.  单击**Web 服务扩展**文件夹。  
  
    3.  在管理控制台的右窗格中，单击**添加一个新的 Web 服务扩展**。  
  
    4.  在**新建 Web 服务扩展**对话框中，单击**添加**。  
  
    5.  在**Add file**对话框中，单击**浏览**选择的文件 <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**，然后单击**确定**.  
  
    6.  配置虚拟目录**ExpenseReport**使用本地路径[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive  
  
     有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
## <a name="running-the-sample"></a>运行示例  
 在降本示例与正确的费用报告一起运行之前，请使用以下过程验证“无错误”情况下的示例是否正常运行。  
  
#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a>验证“无错误”情况下的示例是否正常运行  
  
1.  打开的 InfoPath 窗体**费用报表-John Doe.xml**。 查看**部门**字段在窗体。 此字段应设置为“Marketing”。  
  
2.  在的 InfoPath 窗口的左上角，单击**提交**或单击**重新提交费用报表**。 等待出现确认窗口，指示已成功提交费用报告。  
  
     -或者-  
  
     复制并粘贴到此文件**ExpenseReportIn**文件夹。  
  
3.  你应看到新的文件中放入**ExpenseReportOut**文件夹。 此文件即为上述步骤中提交的费用报告表单。  
  
 在确认“无错误”的情况后，使用以下过程将本示例与不正确的费用报告一起运行，从而触发错误处理功能。  
  
#### <a name="to-trigger-error-handling"></a>触发错误处理  
  
1.  打开的 InfoPath 窗体**无效费用报表-John Doe.xml**。 查看**部门**字段在窗体。 此字段设置为某个无效的值。  
  
2.  在的 InfoPath 窗口的左上角，单击**提交**。 等待出现确认窗口，指示已成功提交费用报告。  
  
     -或者-  
  
     复制并粘贴到此文件**ExpenseReportIn**文件夹。  
  
3.  你应看到名的新文件**ErrorReport_\<***日期*_*时间***\>.xml**中放入**ExpenseReportOut**文件夹。  
  
     打开此文件，然后会观察到这是在前面步骤中提交的费用报告，但在开头添加了错误信息。  
  
4.  将错误部门值替换为"Marketing"，然后单击**提交**的 InfoPath 窗口的左上角。  
  
     -或者-  
  
     复制并粘贴到此文件**ResubmittedReportIn**文件夹。  
  
5.  你应看到在中创建的新文件**ExpenseReportOut**文件夹。 此文件即为重新提交到服务器的更正后的费用报告。  
  
## <a name="see-also"></a>另请参阅  
 [使用失败的邮件路由](../core/using-failed-message-routing.md)   
 [消息传送（BizTalk Server 示例文件夹）](../core/messaging-biztalk-server-samples-folder.md)