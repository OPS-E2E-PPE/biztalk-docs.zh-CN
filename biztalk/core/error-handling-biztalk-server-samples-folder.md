---
title: 错误处理 （BizTalk Server 示例文件夹） |Microsoft Docs
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
ms.openlocfilehash: dfff362d6d12e68ad7c0ef9258cccfd68dff1a0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348200"
---
# <a name="error-handling-biztalk-server-samples-folder"></a>错误处理 （BizTalk Server 示例文件夹）
此示例的目的是生成基于内容的路由 (CBR) 应用程序时的错误处理功能。  

## <a name="prerequisites"></a>先决条件  
 若要运行示例，建议你安装 Microsoft Office InfoPath 2010 或更高版本安装。 您可以运行该示例不使用 InfoPath，但在这种情况下不能查看费用报告以及通过 HTTP 适配器的费用报告的提交。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例实现费用报告处理系统的一部分。 具体而言，此示例执行以下任务：  

1. 定义包含有关费用报告和单个提交者包括部门名称信息的费用报表架构。  

2. 提供用于提交费用报表通过目录或通过使用 InfoPath 的 Web 服务。  

3. 促进**部门**并**correlationID**消息中的属性记录，以便它可用于在端口筛选器中控制路由。  

4. 路由的费用报告属于市场营销部到目录，从而模拟送达该部门的后端系统中的文件。  

5. 生成失败的消息的费用报告属于 Marketing 之外的部门。 失败的消息包括有关错误包括错误代码和错误说明的信息。  

6. 失败消息路由给接收方人员 (业务用户或应用程序操作员) 以进行更正和重新提交。  

7. 路由重新提交费用报告，根据部门上文所述。  

   其中的大部分工作是通过 BizTalk 业务流程调度。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 本设计依赖于默认发送和接收 XML 管道、 属性升级、 订阅筛选器和业务流程计划中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来路由消息。 下表中列出的设计元素和及其选入理由。  


|         设计元素         |                                                                                                                                                                 选择的原因                                                                                                                                                                 |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  默认 XML 接收管道  |                                                        XMLReceive 管道支持属性升级;PassThruReceive 管道却没有。<br />-入站的消息已采用 XML 格式，并且不需要除基本拆装和参与方解析之外的处理。                                                        |
|  为失败消息路由   | -接收端口挂起失败的消息并将默认情况下生成一个否定确认。 启用路由后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]尝试将路由到某个订阅应用程序的处理失败的任何消息 （例如其他接收端口或业务流程计划）。 |
|       属性升级       |                                                                                                   BizTalk Server 根据属性字段进行路由。 可分辨的字段由业务流程使用，并且不能用于路由。                                                                                                   |
|      订阅筛选器       |                                                                                                          -订阅筛选器来执行路由捕获满足一个或多个基于属性的字段的条件的消息。                                                                                                           |
| BizTalk 业务流程调度 |                                                                  -提供了将信息添加到失败的消息的机会。<br />-启用失败消息路由到的人为干预的专用位置。<br />-进程重新提交费用报告。                                                                   |
|          XMLTransmit           |                                                                                                                -执行基本组装传出 XML 消息。 PassThruTransmit 管道未提供其他支持。                                                                                                                 |

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 此示例位于 <`Samples Path>`\Messaging\ErrorHandling\\。  

 下表列出了本示例的文件。  

|文件|Description|  
|----------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除。<br /><br /> 删除发送和接收端口。<br /><br /> 根据需要删除 Internet 信息服务 (IIS) 虚拟目录。|  
|ErrorHandling.sln|该示例的 visual Studio 解决方案文件。|  
|ErrorHandlingBinding.xml|该示例的绑定文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|费用报告-John Doe.xml|示例费用报告 InfoPath 文档。|  
|无效的费用报表-John Doe.xml|使用无效的数据示例费用报告 InfoPath 文档。|  
|在 ErrorHandler 文件夹中：<br /><br /> ErrorHandler.btproj|业务流程的 BizTalk 项目。|  
|在 ErrorHandler 文件夹中：<br /><br /> ResubmitLogic.odx|业务流程的订阅失败的消息、 将其发送到接收方人员进行更正，然后重新提交更正后返回到服务器进行路由的消息。|  
|在 ErrorHandler 文件夹中：<br /><br /> SuspendMessage.odx|用于挂起无法在错误处理业务流程内处理的消息的业务流程。|  
|在 InfoPathForms 文件夹中：<br /><br /> Expense Report.xsn<br /><br /> Expense Report-Resubmit.xsn|费用报告 InfoPath 窗体和窗体用于查看和重新提交失败的消息。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> ExpenseReportSchema.xsd|费用报告文档的 XML 架构。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PipelinesAndSchemas.btproj|该示例的 BizTalk 项目。|  
|在 PipelinesAndSchemas 文件夹中：<br /><br /> PropertySchema.xsd|该示例的属性架构。|  

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 此示例提供了用于创建你自己的错误处理过程的起始点。  

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

#### <a name="to-build-and-initialize-the-compose-sample"></a>若要生成并初始化 Compose 示例  

1. 在命令窗口中，导航到以下文件夹：  

    <`Samples Path`>**\Messaging\ErrorHandling**  

2. 运行**Setup.bat**，该文件将执行以下操作：  

   - 创建三个文件夹：**ExpenseReportIn**， **ExpenseReportOut**，和**ResubmittedReportIn**以下路径下：  

      <`Samples Path`>**\Messaging\ErrorHandling**  

   - 复制并发布 InfoPath 窗体**Expense Report.xsn**并**Expense Report – Resubmit.xsn**到文件夹**C:\Temp\InfoPathForms**。  

   - 编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  

   - 创建一个名为的虚拟目录**为 ExpenseReports**。  

   - 创建新的 BizTalk 应用程序调用**Error Handling Sample**并部署到其中的示例程序集。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置和发送端口和接收端口。  

   - 登记和启动业务流程，启用接收位置，并启动发送端口。  

      如果你选择打开并生成此示例中的项目不运行 Setup.bat 的情况下，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对示例程序集进行签名。  

3. 在尝试运行此示例之前, 确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成或初始化过程中未报告任何错误。  

   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

4. 如果使用 Internet 信息服务 (IIS) 7.0，需要执行其他配置步骤，从而调整与相对应的虚拟目录的设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 接收位置使用的示例。 通过执行以下操作配置 IIS:  

   1. 使用 IIS 7.0 管理器，创建一个新的应用程序池，为 BizTalk Isolated Host Users 组。  

   2. 配置应用程序池的标识下运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]独立主机用户。 (如果已配置为其他应用程序池，可以跳过此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 接收位置。)  

   3. 配置虚拟目录**ExpenseReport**使用 HTTP 接收在上一步中创建的应用程序池。  

      如果你还没有使用 BTSHTTPReceive.dll ISAPI 扩展插件的 Web 服务器扩展插件，创建并启用通过设置其状态为"允许"。 你可以在 IIS 7.0 中使用 IIS 管理控制台 (要么直接下**管理工具**或通过计算机管理控制台)，如下所示：  

   4. 展开**Internet Information Services Manager**树。  

   5. 单击**Web 服务扩展**文件夹。  

   6. 在管理控制台的右窗格中，单击**添加一个新的 Web 服务扩展**。  

   7. 在中**新的 Web 服务扩展**对话框中，单击**添加**。  

   8. 在**添加文件**对话框中，单击**浏览**若要选择的文件 <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**，然后单击**确定**.  

   9. 配置虚拟目录**ExpenseReport**以使用本地路径[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive  

      有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  

## <a name="running-the-sample"></a>运行示例  
 在之前与正确的费用报告一起运行示例，使用以下过程以验证"无错误"case 示例正常运行。  

#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a>若要验证"无错误"正确 case 示例的工作机制  

1. 打开 InfoPath 表单**Expense Report-John Doe.xml**。 看看**部门**字段在窗体中。 此字段应设置为"Marketing"。  

2. 在 InfoPath 窗口的左上角，单击**提交**或单击**重新提交费用报告**。 等待确认窗口，指示已成功提交费用报表。  

    -或-  

    复制并粘贴到此文件**ExpenseReportIn**文件夹。  

3. 应看到新的文件放入**ExpenseReportOut**文件夹。 此文件是相同上述步骤中提交的费用报告表单。  

   确认"无错误"用例后，使用以下过程使用不正确的费用报表来触发错误处理功能运行此示例。  

#### <a name="to-trigger-error-handling"></a>若要触发错误处理  

1. 打开 InfoPath 表单**Invalid Expense Report-John Doe.xml**。 看看**部门**字段在窗体中。 此字段设置为某个无效的值。  

2. 在 InfoPath 窗口的左上角，单击**提交**。 等待确认窗口，指示已成功提交费用报表。  

    -或-  

    复制并粘贴到此文件**ExpenseReportIn**文件夹。  

3. 您应看到名为的新文件**ErrorReport_\<**<em>日期</em>_<em>时间</em>**\>.xml**放到**ExpenseReportOut**文件夹。  

    打开此文件并观察，这是上一步中，但在开头添加错误信息提交的费用报告。  

4. 错误的部门值替换为"Marketing"，然后依次**提交**在 InfoPath 窗口的左上角。  

    -或-  

    复制并粘贴到此文件**ResubmittedReportIn**文件夹。  

5. 应看到新的文件中创建**ExpenseReportOut**文件夹。 此文件是为重新提交到服务器的更正后的费用报告。  

## <a name="see-also"></a>请参阅  
 [使用失败的消息路由](../core/using-failed-message-routing.md)   
 [消息传送（BizTalk Server 示例文件夹）](../core/messaging-biztalk-server-samples-folder.md)