---
title: 补偿 （BizTalk Server 示例） |Microsoft Docs
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
- compensations, examples
- examples, compensations
- compensations, orchestrations
ms.assetid: 9d10c7be-6a4c-44cc-bf29-78ecdf147bd1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56675a59714a6fabc1d54fdb594466c7568cfeba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973446"
---
# <a name="compensation-biztalk-server-sample"></a>补偿 （BizTalk Server 示例）
补偿示例演示如何使用**补偿**形状在业务流程中的。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示如何补偿业务流程中已提交的事务，步骤顺序如下：  
  
1.  在 InfoPath 表单中输入客户数据，然后向已公开为 Web Services 的业务流程提交该数据。  
  
2.  该业务流程有两个并行操作。 一个将返回 InfoPath 表单的确认，另一个将更新 Northwind 和 BTSCompensationSampleMailingList 数据库。  
  
3.  在第二个操作中，业务流程将传入消息映射为客户关系管理 (CRM) 应用程序消息格式，然后更新**客户**Northwind 数据库中的表。 此更新完成后，将会更新 BTSCompensationSampleMailingList 数据库中的 Mailing List 表。  
  
4.  如果以上两个更新中有一个失败，则会通过调用外部程序集将原始客户数据重新写入数据库来补偿对 Northwind 数据库所做的更改。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 一个**作用域**形状主要用于事务性执行和异常处理，包括补偿。 作用域由两个模块组成。 第一个模块为上下文模块，第二个模块为一个或多个异常处理模块或补偿模块。 这与 .NET 编程语言中的 try-catch 语句类似。 在 UpdateContact.odx 业务流程中有两个并行操作。 在右侧分支，是在 try 块**作用域**形状名为更新后端系统，它具有一个长时间运行的事务类型和事务标识符为 Upd_Backend。 沿流继续向下，有一个 catch 模块，用于捕获常规异常并启动补偿。  
  
 有关详细信息**作用域**形状中，请参阅[作用域](../core/scopes.md)。 另请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。  
  
> [!NOTE]
>  业务流程本身必须为长期事务才能将事务类型设置为“原子”或“长期”。  
  
 在 try 块中，有两个名为的作用域**Update CRM**并**Update Mailing**。 这两个作用域都是原子事务。 在 Update CRM 作用域中，有一个 try 模块和一个补偿模块。 try 模块通过调用外部程序集中的方法来更新 Northwind 数据库。 补偿模块执行补偿操作。 当 Update Backend Systems 作用域中发生异常时，Undo CRM 表达式形状中的代码将把记录重新更新为它的原始状态。 这由触发**补偿**捕获异常块中的形状。  
  
> [!NOTE]
>  原子事务保证在事务性更新期间发生故障时可自动回滚任何部分更新，并且消除事务的影响（事务中进行的任何 .NET 调用的影响除外）。  
  
> [!NOTE]
>  长期事务中的最后一个语句完成时，代表该事务已提交。 事务中止的情况下，不会自动回滚状态。 这种回滚可以通过编写如本示例所示的异常处理程序和补偿处理程序来实现。  
  
 在 catch 块中，还有一个**延迟**形状设置为十秒。 它用于延迟补偿操作。 此外，还有**补偿**启动补偿操作用于在 Upd_Backend 事务中的形状。  
  
 业务流程接收到输入消息后，将发生以下情况：  
  
1.  UpdateCrm 程序集更新 Northwind 数据库中的行。  
  
2.  UpdateMailingList 程序集更新 BTSCompensationSampleMailingList 数据库中的匹配记录。  
  
3.  如果更新 Northwind 数据库时发生故障，将会引发异常并且业务流程会退出进程。  
  
4.  如果更新 BTSCompensationSampleMailingList 数据库时发生故障，将会引发异常，并且在延迟十秒钟后将原始客户数据重新写回 Northwind 数据库。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Orchestrations\Compensation\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于卸载示例的批处理文件。|  
|CompensationOrchestration.btproj|业务流程项目。|  
|CompensationSample.sln|示例解决方案。|  
|CompensationSampleBinding.xml|业务流程的绑定数据（安装期间使用）。|  
|ContactInfo.xsd|联系人信息消息架构。|  
|ContactInfo.xsx|业务流程设计器布局文件。|  
|CreateSQLDataStore.sql|用于创建和填充示例数据库的 SQL 脚本。|  
|CrmSchema.xsd|CRM 更新消息架构。|  
|MailingListSchema.xsd|邮件列表消息更新架构。|  
|RemoveVirDir.vbs|Microsoft Visual Basic Scripting Edition (VBScript) 脚本，用于删除 Web Services 虚拟目录和物理目录（卸载期间使用）。|  
|Request2Crm.btm|用于将请求（联系信息）翻译为 CRM 更新消息的消息映射。|  
|Request2MailingList.btm|用于将请求（联系信息）翻译为邮件列表消息的消息映射。|  
|Setup.bat|用于安装此示例的批处理文件。|  
|UpdateContact.odx|业务流程文件。|  
|UpdateRequest2UpdateResponse.btm|用于将请求（联系信息）翻译为响应消息的消息映射。|  
|UpdateResponse.xsd|响应消息架构。|  
|InfoPath\Contact Info Update.xsn|用于将表单提交给业务流程 Web Services 的 Microsoft InfoPath 文件。|  
|UpdateCrm\AssemblyInfo.cs|UpdateCrm 程序集的程序集信息源文件。 （UpdateCrm 程序集更新 Northwind 数据库。）|  
|UpdateCrm\UpdateCrm.cs|UpdateCrm 程序集的源代码主文件。|  
|UpdateCrm\UpdateCRM.csproj|UpdateCrm 项目文件。|  
|UpdateMailingList\AssemblyInfo.cs|UpdateMailingList 程序集的程序集信息源文件。 （UpdateMailingList 程序集更新示例数据库。）|  
|UpdateMailingList\UpdateMailingList.cs|UpdateMailingList 程序集的源代码主文件。|  
|UpdateMailingList\UpdateMailingList.csproj|UpdateMailingList 项目文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化本示例  
  
#### <a name="to-build-and-initialize-the-compensation-sample"></a>生成并初始化补偿示例  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Orchestrations\Compensation\  
  
2. 运行 Setup.bat，该文件将执行以下操作：  
  
   -   生成并部署示例程序集。  
  
   -   当 BizTalk Web Services 发布向导启动时，请手动执行以下操作：  
  
   1.  上**欢迎使用 BizTalk Web Services 发布向导**页上，单击**下一步**。  
  
   2.  上**创建 Web 服务**页上，选择**发布 BizTalk 业务流程作为 web 服务**，然后单击**下一步**。  
  
   3.  上**BizTalk 程序集**页上，浏览并选择\<*示例路径*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll，并单击**下一步**。  
  
   4.  上**业务流程和端口**页上，单击**下一步**。  
  
   5.  上**Web 服务属性**页上，在**web 服务的目标命名空间**，类型**http://Microsoft.BizTalk.Samples.Compensation/**，然后单击**下一步**。  
  
   6.  上**Web 服务项目**页上，在**位置**，类型**http://localhost/CompensationOrchestrationWebServiceProxy**。  
  
   7.  选择**允许匿名访问 web 服务**复选框。  
  
   8.  选择**创建 BizTalk 接收位置在以下应用程序中**复选框。  
  
   9. 在中**创建 BizTalk 接收位置在以下应用程序中**下拉列表菜单中，选择**BizTalk Application 1**从下拉列表中，然后单击**下一步**。  
  
   10. 上**Web Services 项目摘要**页上，单击**创建**。  
  
   11. 上**完成 BizTalk Web Services 发布向导**页上，单击**完成**。  
  
3. 安装程序会创建并绑定端口，为该示例创建后端数据库，还会将 C# 程序集添加到全局程序集缓存。  
  
   > [!NOTE]
   >  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
 生成并初始化本示例后，请先考虑以下情况，然后再运行本示例：  
  
- 如果要在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 上运行本示例，必须创建 IIS 应用程序池并将其身份设置为揃“BizTalk Application Users Windows”组的成员帐户。 在此应用程序池内运行还需要更新业务流程 Web Services 虚拟目录。  
  
- 将“ASPNET”帐户添加到“Biztalk Isolated Host Users”组。  
  
- 将该 BizTalk Application Users 组 db_owner 权限授予**BTSCompensationSampleMailingList**并**Northwind**数据库。  
  
- 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未安装在默认位置 (驱动器： files\microsoft BizTalk Server\<版本\>\\)，您必须发布 Contact Info Update.xsn 表单，然后才能使用它。 若要这样做，请执行以下操作。  
  
  #### <a name="to-publish-the-infopath-form"></a>发布 InfoPath 表单  
  
  1.  在 Internet Explorer 中，在**工具**菜单上，单击**Internet 选项**。  
  
  2.  上**安全**选项卡上，单击**Internet**，然后单击**自定义级别**。  
  
  3.  在中**杂项**部分中，确保**跨域访问数据源**设置已启用，然后依次**确定**。 InfoPath 用户界面解决方案脚本代码需要此设置才能运行。  
  
  4.  在 Windows 资源管理器，导航到\<*示例路径*\>\Orchestrations\Compensation\InfoPath，右键单击**Contact Info Update.xsn** ，然后单击**设计**。  
  
  5.  InfoPath Contact Info Update 解决方案以设计模式打开。  
  
  6.  在 InfoPath Contact Info Update 应用程序上**文件**菜单上，单击**发布**。  
  
  7.  此时，将显示发布向导。  
  
  8.  选择**到此计算机上或在网络上的共享文件夹**并将解决方案发布到该路径\<*示例路径*\>\Orchestrations\Compensation\InfoPath\Contact InfoUpdate.xsn。  
  
  9. 关闭设计模式下的 InfoPath。  
  
- 现在可以运行本示例了。  
  
  #### <a name="to-run-the-compensation-sample"></a>运行补偿示例  
  
  1.  双击**Contact Info Update.xsn**在 InfoPath 中打开它。  
  
  2.  使用在两个数据库中都存在的某一帐户填写该表单。 例如，使用 Northwind Customers 表中的现有帐户 ID“ALFKI”。  
  
  3.  上**文件**菜单中，选择**提交**，然后单击**提交**。  
  
  4.  响应文档应显示在\<*示例路径*\>\Orchestrations\Compensation\Out 文件夹中，和 Northwind 和 BTSCompensationSampleMailingList 数据库都应更新使用 InfoPath 窗体中的新数据。  
  
      > [!NOTE]
      >  你可以分离 BTSCompensationSampleMailingList 数据库或将其脱机以测试该业务流程执行的补偿操作。 观察相应记录是否先在 Northwind 数据库中进行了更新。 然后，在该业务流程尝试更新 BTSCompensationSampleMailingList 数据库时，因为该数据库已经分离，更新将失败。 因此，将引发异常，并在 10 秒钟的延迟后，就会采取补偿操作将原始客户数据写回 Northwind 数据库。  
  
      > [!NOTE]
      >  你可能会收到“用户‘IIS APPPOOL\DefaultAppPool’登录失败”错误。 这可能是因为基于令牌的服务器访问验证失败所致。 若要解决此错误，请创建一个新的应用程序池并在该池中使用管理帐户。  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-compensation-sample"></a>卸载补偿示例  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Orchestrations\Compensation\  
  
2. 运行 Cleanup.bat。  
  
## <a name="see-also"></a>请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)