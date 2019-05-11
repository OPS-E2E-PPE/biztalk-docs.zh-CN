---
title: ExpenseReportSubmission |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
ms.assetid: d0bacab3-7092-44b8-a1c6-6f574a2db8bd
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195aa719fbea17839fae33340af81d9ecc626462
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346166"
---
# <a name="expensereportsubmission"></a>ExpenseReportSubmission
ExpenseReportSubmission 示例演示了如何将文档提交到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从诸如 Microsoft Excel 之类的丰富客户端的业务流程。  

 富客户端，可在客户端上执行多个操作，如数据验证和基本计算。 这有助于最大程度减少与后端服务器，这可能很有用，当只有低带宽连接可用时的交互。  

## <a name="prerequisites"></a>先决条件  
 必须确保你的开发环境是配置且能够与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web 服务。 有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示如何提交费用报告到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]直接从 Excel 中，使用以下步骤序列：  

1. 用户执行 Excel 电子表格中提供的手动示例步骤。  

2. 电子表格中的宏代码将电子表格数据转换为可扩展标记语言 (XML) 格式，并将对该 XML 消息提交[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 HTTP 连接。  

3. 运行的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]检索 XML 费用报告消息、 验证通过提供的架构，其格式，然后将它放到另一个文件夹。  

4. 在实践中，以外的此示例中，如企业资源规划 (ERP) 系统的另一个应用程序然后将检索电子表格文件以进一步处理。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\AdaptersUsage\ExpenseReportSubmission\  

 下表显示了本示例中的文件及其用途说明：  


|                                                            文件                                                            |                                                                                           Description                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                          Cleanup.bat                                                          | 取消部署程序集，并将其从全局程序集缓存 (GAC) 中;删除发送和接收端口;根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。 |
|                                                    ExpenseReport.15.3.xls                                                     |                                              使用费用报告布局、 相关联的宏和按钮调用这些宏的 Excel 电子表格。                                              |
|                                                      MessageExample.xml                                                       |                                                                            XML 费用报告格式示例。                                                                             |
|                                                           Setup.bat                                                           |                                                                               生成并初始化本示例。                                                                                |
| 在 \BTSExpenseDemo 文件夹中：<br /><br /> AssemblyInfo.cs、<br /><br /> BTSExpenseDemo.btproj,<br /><br /> BTSExpenseDemo.sln |                                                                  提供了项目、 解决方案和相关的文件，此示例。                                                                  |
|                             在 \BTSExpenseDemo 文件夹中：<br /><br /> BTSExpenseDemoBinding.xml                              |                                                                         用于如端口绑定之类的自动设置。                                                                          |
|                            在 \BTSExpenseDemo 文件夹中：<br /><br /> BTSExpenseOrchestration.odx                             |                                   提供了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为本示例的业务流程。                                   |
|                              在 \BTSExpenseDemo 文件夹中：<br /><br /> SchemaExpenseReport.xsd                               |                                                                       提供有关 XML 费用报告格式的架构。                                                                       |

### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*示例路径*\>\AdaptersUsage\ExpenseReportSubmission  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 编译 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目对于此示例，并部署生成的程序集。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送和接收端口。  

     > [!NOTE]
     >  此示例将显示以下警告时创建并绑定端口：  
     >   
     >  `Warning: Receive handler not specified for receive location "BTSExpenseReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host` 的用户。  
     >   
     >  您可以放心地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用该接收位置，并启动发送端口。  

   - 配置 IIS。  

   - 绑定并启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程。  

   - 将 HTTP 地址设置为所需的 Excel 电子表格的位置。  

   > [!NOTE]
   >  有关 BizTalk ISAPI 筛选器的详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
   > 
   > [!NOTE]
   >  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
   > 
   > [!NOTE]
   >  如果你选择打开并生成本示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
   > 
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

3. Setup.bat 文件将配置此示例中使用默认网站相关联的 IIS 应用程序池运行的虚拟目录。  若要配置本示例中的用户上下文中运行的虚拟目录**BizTalk Isolated Host Users**并**IIS_WPG**用户组，应配置要运行在新的虚拟目录IIS 应用程序池。  配置要通过完成以下步骤在新的 IIS 应用程序池中运行的虚拟目录：  

   > [!NOTE]
   >  如果已创建一个新的应用程序池的另一个 SDK 示例然后则可以转到最后一个项目符号项下。  

   1.  单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  

   2.  在中**Internet 信息服务 (IIS) 管理器**，导航到**应用程序池**文件夹。  

   3.  右键单击**应用程序池**文件夹，然后单击**新建**，**应用程序池...**  

   4.  输入的名称**应用程序池 ID:** 如 BizTalkSDKSamples，确认**对新应用程序池使用默认设置**选项已选中，然后单击**确定**到创建新的应用程序池。  

   5.  右键单击新的应用程序池，然后单击**属性**。  

   6.  单击**标识**选项卡的属性对话框并更改用于成员的用户运行此应用程序池标识**BizTalk Isolated Host Users**用户组。  此用户还应是本地组成员的**IIS_WPG**用户组。  

   7.  配置此 SDK 示例的新应用程序池下运行的虚拟目录。 **应用程序池：** 设置位于**虚拟目录**选项卡的虚拟目录属性对话框。 此示例为创建的虚拟目录**ExpenseReportSubmission**。  

4. 将 web 服务扩展为 HTTPReceive.dll 添加到 IIS  

   1.  在中**Internet 信息服务 (IIS) 管理器**，导航到**Web 服务扩展**文件夹。  

   2.  右键单击**Web 服务扩展**文件夹，然后选择**添加一个新的 Web 服务扩展**以显示**新 Web 服务扩展**对话框。  

   3.  输入**ExpenseReportSubmission**为**扩展插件名称：**  

   4.  单击**外**以显示**添加文件**对话框。  

   5.  单击**浏览**以显示**打开**对话框框中，导航到 *\<BizTalk Server 安装文件夹\>* \HttpReceive\BTSHTTPReceive.dll，然后单击**开放**，然后单击**确定**。  

   6.  启用选项**为允许设置扩展状态**然后单击**确定**。  

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 ExpenseReportSubmission 示例。  

> [!NOTE]
>  如果使用 Microsoft Excel 的增强的安全功能，在电子表格中的宏可能会禁用。 请遵循 Excel 提供的有关如何从受信任的源运行未签名的宏的说明进行操作。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  打开 Excel 文件 ExpenseReport.15.3.xls 此示例随附。  

2.  （可选） 更改电子表格中的示例数据，而不更改其格式。  

3.  在电子表格中，单击**启动**来执行本地计算。  

     从更改按钮的文本**启动**到**提交**。  

4.  在电子表格中，单击**提交**。  

5.  观察到的已提交的消息、 表具有黄色背景 （单元格 C7） 上方的结果和实际返回代码和文本说明下方和右侧 （单元格 G23） 的文本。  

     如果提交失败，重试。 另请参阅备注部分中的故障排除表。  

## <a name="comments"></a>注释  
 此类情况可以发生的例如，现场销售人员配备有较旧版本的 Microsoft Windows 不支持.NET Framework 中，并为其升级到更高版本的 Windows 的要求是不可行的选项。  

 在此示例中演示的重要功能是：  

- 提交从胖客户端 （非。NET-based)  

- Microsoft Office 集成  

- HTTP 接收连接  

- 简单的业务流程  

- 文件适配器  

  下表显示了一些可能的提交错误和其解决方案。  

|HTTP 错误代码|可能的操作|  
|---------------------|---------------------|  
|401 未经授权|启用匿名访问虚拟目录。|  
|503 服务不可用，以及介于 400 和 500 范围中的大多数其他 HTTP 代码|确保主机运行，并且该服务是部署、 绑定到正确的端口，并启动。|  

## <a name="see-also"></a>请参阅  
 [适配器示例 - 用法](../core/adapter-samples-usage.md)