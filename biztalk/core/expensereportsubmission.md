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
ms.openlocfilehash: 09cec8e16b8b145206a2cd6b2a30859e502ce8b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967894"
---
# <a name="expensereportsubmission"></a>ExpenseReportSubmission
ExpenseReportSubmission 示例演示了如何从胖客户端（如 Microsoft Excel）向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程提交文档。  

 胖客户端允许在客户端上执行多种操作，如数据验证和基本计算。 这有助于最大程度地减少与后端服务器的交互，当只有低带宽连接可用时，将十分有用。  

## <a name="prerequisites"></a>必要條件  
 必须确保您的开发环境已正确配置且能够使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web Services。 有关详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  

## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示如何使用以下一系列步骤直接从 Excel 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提交费用报告：  

1. 用户执行 Excel 电子表格中提供的手动示例步骤。  

2. 电子表格中的宏代码将电子表格数据转换为可扩展标记语言 (XML) 格式，并使用 HTTP 连接将该 XML 消息提交给 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

3. 运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机检索该 XML 费用报告消息，使用提供的架构验证报告格式，然后将它放到另一个文件夹中。  

4. 在实际使用中，另一个应用程序（如企业资源规划 (ERP) 系统）随后会检索该电子表格文件以进一步处理，但这已经超出了本示例的范围。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\AdaptersUsage\ExpenseReportSubmission\  

 下表显示了本示例中的文件及其用途说明：  


|                                                            文件                                                            |                                                                                           Description                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                          Cleanup.bat                                                          | 取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。 |
|                                                    ExpenseReport.15.3.xls                                                     |                                              Excel 电子表格，包含费用报告布局、相关联的宏及调用这些宏的按钮。                                              |
|                                                      MessageExample.xml                                                       |                                                                            XML 费用报告格式示例。                                                                             |
|                                                           Setup.bat                                                           |                                                                               生成并初始化本示例。                                                                                |
| 在 \BTSExpenseDemo 文件夹中：<br /><br /> AssemblyInfo.cs、<br /><br /> BTSExpenseDemo.btproj、<br /><br /> BTSExpenseDemo.sln |                                                                  提供本示例的项目、解决方案和相关文件。                                                                  |
|                             在 \BTSExpenseDemo 文件夹中：<br /><br /> BTSExpenseDemoBinding.xml                              |                                                                         用于如端口绑定之类的自动设置。                                                                          |
|                            在 \BTSExpenseDemo 文件夹中：<br /><br /> BTSExpenseOrchestration.odx                             |                                   提供本示例的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。                                   |
|                              在 \BTSExpenseDemo 文件夹中：<br /><br /> SchemaExpenseReport.xsd                               |                                                                       提供 XML 费用报告格式的架构。                                                                       |

### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  

1. 在命令窗口中，导航到下面的文件夹：  

    \<*示例路径*\>\AdaptersUsage\ExpenseReportSubmission  

2. 运行 Setup.bat 文件，该文件将执行以下操作：  

   - 编译本示例的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，并部署生成的程序集。  

   - 创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。  

     > [!NOTE]
     >  在创建并绑定端口时，本示例将显示以下警告：  
     >   
     >  `Warning: Receive handler not specified for receive location "BTSExpenseReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`的用户。  
     >   
     >  可以安全地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用接收位置并启动发送端口。  

   - 配置 IIS。  

   - 绑定并启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。  

   - 将 HTTP 地址设置为 Excel 电子表格需要的位置。  

   > [!NOTE]
   >  有关 BizTalk ISAPI 筛选器的详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
   > 
   > [!NOTE]
   >  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
   > 
   > [!NOTE]
   >  如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须首先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。 使用此密钥对生成程序集进行签名。  
   > 
   > [!NOTE]
   >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

3. setup.bat 文件将本示例的虚拟目录配置为在与默认网站相关联的 IIS 应用程序池中运行。  若要配置本示例中的用户上下文中运行的虚拟目录**BizTalk Isolated Host Users**并**IIS_WPG**用户组，应配置要运行在新的虚拟目录IIS 应用程序池。  通过完成以下步骤，可将虚拟目录配置为在新的 IIS 应用程序池中运行：  

   > [!NOTE]
   >  如果已经为另一个 SDK 示例创建了新的应用程序池，可继续进行以下步骤中的最后一项。  

   1.  单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  

   2.  在中**Internet 信息服务 (IIS) 管理器**，导航到**应用程序池**文件夹。  

   3.  右键单击**应用程序池**文件夹，然后单击**新建**，**应用程序池...**  

   4.  输入的名称**应用程序池 ID:** 如 BizTalkSDKSamples，确认**对新应用程序池使用默认设置**选项已选中，然后单击**确定**到创建新的应用程序池。  

   5.  右键单击新的应用程序池，然后单击**属性**。  

   6.  单击**标识**选项卡的属性对话框并更改用于成员的用户运行此应用程序池标识**BizTalk Isolated Host Users**用户组。  此用户还应是本地组成员的**IIS_WPG**用户组。  

   7.  将本 SDK 示例的虚拟目录配置为在新应用程序池下运行。 **应用程序池：** 设置位于**虚拟目录**选项卡的虚拟目录属性对话框。 此示例为创建的虚拟目录**ExpenseReportSubmission**。  

4. 在 IIS 中为 HTTPReceive.dll 添加一个 Web 服务扩展  

   1.  在中**Internet 信息服务 (IIS) 管理器**，导航到**Web 服务扩展**文件夹。  

   2.  右键单击**Web 服务扩展**文件夹，然后选择**添加一个新的 Web 服务扩展**以显示**新 Web 服务扩展**对话框。  

   3.  输入**ExpenseReportSubmission**为**扩展插件名称：**  

   4.  单击**外**以显示**添加文件**对话框。  

   5.  单击**浏览**以显示**打开**对话框框中，导航到 *\<BizTalk Server 安装文件夹\>* \HttpReceive\BTSHTTPReceive.dll，然后单击**开放**，然后单击**确定**。  

   6.  启用选项**为允许设置扩展状态**然后单击**确定**。  

## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 ExpenseReportSubmission 示例。  

> [!NOTE]
>  如果使用的是 Microsoft Excel 的增强安全功能，则电子表格中的宏可能会被禁用。 请遵循 Excel 提供的有关如何运行来自受信任来源的未签名宏的说明进行操作。  

#### <a name="to-run-this-sample"></a>运行本示例的步骤  

1.  打开本示例附带的 Excel 文件 ExpenseReport.15.3.xls。  

2.  （可选）更改电子表格中的示例数据但是不更改其格式。  

3.  在电子表格中，单击**启动**来执行本地计算。  

     从更改按钮的文本**启动**到**提交**。  

4.  在电子表格中，单击**提交**。  

5.  观察所提交消息的文本、黄色背景的表（单元格 C7）上方的结果以及下方和右侧（单元格 G23）的实际返回代码和文本说明。  

     如果提交失败，请重试。 另请参阅“注释”部分中的故障排除表。  

## <a name="comments"></a>注释  
 这种情况是可能发生的，例如，某位现场销售人员配有不支持 .NET Framework 的 Microsoft Windows 早期版本，并且升级到较新版本的 Windows 也不可行。  

 本示例中演示的重要功能包括：  

- 从胖客户端（不基于 .NET）进行提交  

- Microsoft Office 集成  

- HTTP 接收连接  

- 简单业务流程  

- 文件适配器  

  下表显示了一些可能的提交错误及其解决方案。  

|HTTP 错误代码|可能的操作|  
|---------------------|---------------------|  
|401 未经授权|在虚拟目录上启用匿名访问。|  
|503 服务不可用，以及大多数介于 400 和 500 之间的其他 HTTP 代码|确保主机运行，并将服务部署、绑定到正确的端口并启动。|  

## <a name="see-also"></a>请参阅  
 [适配器示例 - 用法](../core/adapter-samples-usage.md)