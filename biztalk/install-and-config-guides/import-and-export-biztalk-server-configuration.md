---
title: 导入和导出 BizTalk Server 配置 |Microsoft Docs
description: 步骤应用，导入、 导出或取消配置组件，并更新数据库和 BizTalk Server 中的服务帐户
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6206ed8-d087-44cc-8ab5-da5d8a28e09a
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60faef2bf700a5e7fa1f5ced556e9fdd572201b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980734"
---
# <a name="import-and-export-biztalk-server-configuration"></a>导入和导出 BizTalk Server 配置
“BizTalk Server 配置”可提供对本地计算机上已安装功能的配置状态的高级分析。 使用该工具，可以配置功能或取消对功能的配置、配置安全设置，以及导入和导出配置。  
  
## <a name="prerequisites-to-use-the-biztalk-server-configuration"></a>使用 BizTalk Server 配置的先决条件  
   
-   以登录的帐户必须是本地管理员组的成员，并在 SQL Server 上拥有系统管理员权限。  
  
-   “BizTalk Server 配置”中列出的由 BizTalk Server 生成的默认帐户是本地组。 在多服务器环境中，用域组替换这些本地组。  
  
-   如果配置，以登录的帐户必须是 OLAP 计算机上的 OLAP Administrators 组的成员。  
  
    > [!NOTE]
    >  如果更改组成员身份的当前登录的用户，并且组也是域的成员，为确保注销，并完成所做的更改然后重新登录。 如果您没有登录扩展/登录回原位，您会被拒绝访问新的组成员身份不反映由当前登录名。  
  
## <a name="apply-the-configuration"></a>应用配置  
  
1.  在“BizTalk Server 配置”中，单击“应用配置”。  
  
2.  在“摘要”屏幕上，检查配置，然后单击“下一步”。  
  
3.  在“完成”屏幕上，单击“完成”。  
  
## <a name="import-configuration"></a>导入配置

> [!IMPORTANT]
> 当您导入配置文件时，请确认配置文件不会配置未在您配置 BizTalk Server 安装的组件。 尝试配置 BizTalk Server 上不存在的组件可能造成死锁情况。 在此情况下，取消对依赖的组件的配置文件尝试配置的组件。 但是，尝试取消对依存组件可能要求缺少的组件都存在并且配置。 若要解决此问题，必须编辑配置文件以删除对已卸载的组件的引用，或将配置文件应用到 BizTalk Server 的兼容安装。  
> 
>  除非您已手动编辑该文件导入的配置文件中不保存密码和备份文件位置。 如果已配置的功能，它们将不导入。  
  
  
1.  在“BizTalk Server 配置”中，单击“导入配置”。  
  
2.  在“打开”对话框中，选择要导入的配置文件，然后单击“打开”。  
  
3.  在“BizTalk Server 配置”中，单击“应用配置”。  
  
4.  在“摘要”屏幕上，检查配置，然后单击“下一步”。  
  
5.  在“完成”屏幕上，单击“完成”。  

可以导入 BizTalk Server 使用 BizTalk Server 配置框架的配置文件。 若要深入了解如何使用这些文件，请参阅[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)。  
  
## <a name="export-configuration"></a>导出配置

> [!NOTE]
>  配置文件中将不保存密码。    
 
1. 在“BizTalk Server 配置”中，单击“导出配置”。  
  
2. 在“另存为”对话框中，键入要保存的文件的名称，然后单击“保存”。  

   您可以导出 BizTalk Server 配置使用 BizTalk Server 配置框架。 有关使用这些文件的详细信息，请参阅[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)  
  
## <a name="unconfigure-features"></a>取消对功能的配置  
 通过在“BizTalk Server 配置”中删除 BizTalk Server 功能，您可以在计算机上取消对这些功能的配置。  
  
> [!NOTE]
>  在取消对功能的配置前，应先关闭 BizTalk Server 管理控制台。  
  
 
1.  在“BizTalk Server 配置”中，单击“取消对功能的配置”。  
  
2.  在“取消对功能的配置”对话框，选择要删除的功能，然后单击“确定”。  
  
    > [!NOTE]
    >  此时，将显示一个对话框，警告您将取消对所选功能的配置。 单击“是”继续。  
  
3.  在“摘要”屏幕上，检查配置，然后单击“下一步”。  
  
4.  在“完成”屏幕上，单击“完成”。  
  
## <a name="update-databases"></a>更新数据库  
 您可通过在“BizTalk Server 配置”中编辑与 BizTalk Server 功能相关联的数据库服务器和数据库来更改这些服务器和数据库。  
  
> [!NOTE]
>  支持根据 SQL Server 默认实例和命名实例来配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
> 
>  此工具允许对数据库进行批量编辑。  
  
 
1.  在“BizTalk Server 配置”中，依次单击“视图”和“数据库”。  
  
2.  在“数据库”对话框中，选择要编辑的功能，然后单击“编辑”。  
  
3.  在“数据库”对话框中，键入要使用的数据库服务器名称和数据库名称，然后单击“确定”。  
  
4.  在“数据库”对话框中，单击“关闭”。  
  
## <a name="update-service-accounts"></a>更新服务帐户  
 您可通过在“BizTalk Server 配置”中编辑与 BizTalk Server 功能相关联的服务帐户来更改这些帐户。  
  
> [!NOTE]
>  此工具允许对帐户进行批量编辑。  
  
1.  在“BizTalk Server 配置”中，依次单击“视图”和“服务帐户”。  
  
2.  在“服务帐户”对话框中，选择要编辑的功能，然后单击“编辑”。  
  
3.  在“用户凭据”对话框中，键入要使用的用户名和密码，然后单击“确定”。  
  
4.  在“服务帐户”对话框中，单击“关闭”。  
  
## <a name="see-also"></a>请参阅  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)   