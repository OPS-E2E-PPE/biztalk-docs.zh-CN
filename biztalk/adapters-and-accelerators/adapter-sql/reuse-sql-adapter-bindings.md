---
title: "重用 SQL 适配器绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc8140f-1d40-492c-bce1-b85e992b3567
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67868f20426228c71bad2ef1f1f35e2e49299929
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reuse-sql-adapter-bindings"></a>重用 SQL 适配器绑定
绑定创建的逻辑终结点 （如业务流程端口或角色链接） 和物理终结点之间的映射 (如发送和接收端口)。 这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。 你可以通过使用创建绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="what-is-a-binding-file"></a>什么是绑定文件？  
 绑定文件是一个包含每个 BizTalk 业务流程的作用域中的 BizTalk 程序集、 应用程序或组的绑定信息的 XML 文件。 绑定文件描述：  
  
-   每个业务流程绑定到主机。  
  
-   主机的信任级别。  
  
-   每个设置发送端口、 接收端口、 接收位置和已配置的当事方。  
  
 你可以生成绑定文件，并将它们包含的绑定应用于一个程序集，应用程序或组。 这样可以防止无需在不同的部署环境中手动配置绑定，加快应用程序部署。  
  
 BizTalk 程序集，应用程序，或组不自动生成一个绑定文件。 但是，你可以通过导出绑定生成绑定文件。 同样，然后可以导入的应用程序或组的绑定文件。 本部分提供有关如何导入和导出绑定的说明。  
  
 有关绑定和绑定文件有关的详细信息，请参阅[绑定文件和应用程序部署](../../core/binding-files-and-application-deployment.md)。  
  
## <a name="prerequisites"></a>先决条件  
使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员或 BizTalk 操作员组。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。
 
## <a name="export-bindings"></a>导出绑定
本部分介绍如何导出到 XML 文件的 BizTalk 应用程序的绑定。 您然后可以从 XML 文件到另一个 BizTalk 应用程序来导入绑定。 导入绑定将覆盖任何现有的应用程序中相同的名称绑定。 你还可以向应用程序，不会覆盖现有绑定添加绑定。 在导入应用程序之前，你添加的绑定不会生效。  
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击你想要导出，其的绑定选择的应用**导出**，然后选择**绑定**。  
  
4.  上**导出绑定**页上，在**导出到文件**，键入要导出绑定到 XML 文件的绝对路径。  
  
     例如，输入`C:\Bindings\Application1Bindings.Binding1.xml`  
  
5.  确认**导出当前应用程序中的所有绑定**选择。  
  
6.  若要导出的组的所有方信息，请选择**都导出全局方信息**复选框。  
  
7.  选择“确定”。 绑定将导出到 XML 文件中指定的位置。  

## <a name="import-bindings"></a>导入的绑定
导入使用 BizTalk Server 管理控制台的绑定。
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击你要向其中导入的绑定中，选择应用的程序**导入**，然后选择**绑定**。  
  
4.  选择绑定文件，然后选择**打开**。  
  
绑定文件中的项目将写入该应用程序中。 这些项目显示在该应用程序的相应文件夹中。 例如，发送端口导入的绑定显示在下一部分**发送端口**文件夹。  

## <a name="passwords-are-removed"></a>不会保留密码  
出于安全原因，当导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从文件中删除绑定的密码。 在导入绑定后，必须为发送端口和接收位置重新配置密码，它们才能正常运行。 传输属性对话框中配置密码[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台为发送端口或接收位置。 

有关指定用户名和密码的信息，请参阅[配置 SQL Server 的登录凭据](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)。
  
## <a name="see-also"></a>另请参阅  
[开发具有 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)