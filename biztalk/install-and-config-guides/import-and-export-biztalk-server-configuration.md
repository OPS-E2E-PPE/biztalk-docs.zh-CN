---
title: 导入和导出 BizTalk Server 配置 |Microsoft 文档
description: 步骤，若要应用，导入、 导出或取消配置组件，并更新数据库和 BizTalk Server 中的服务帐户
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
ms.openlocfilehash: 4d0d2ae3f94c0ced65c65fd36dc3499c93ce40b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300125"
---
# <a name="import-and-export-biztalk-server-configuration"></a>导入和导出 BizTalk Server 配置
“BizTalk Server 配置”可提供对本地计算机上已安装功能的配置状态的高级分析。 使用该工具，可以配置功能或取消对功能的配置、配置安全设置，以及导入和导出配置。  
  
## <a name="prerequisites-to-use-the-biztalk-server-configuration"></a>使用 BizTalk Server 配置的先决条件  
   
-   作为登录的帐户必须是本地管理员组的成员，并在 SQL Server 上拥有系统管理员权限。  
  
-   “BizTalk Server 配置”中列出的由 BizTalk Server 生成的默认帐户是本地组。 在多服务器环境中，替换域组这些本地组。  
  
-   如果配置，作为登录帐户必须是 OLAP 在计算机上，OLAP 管理员组的成员。  
  
    > [!NOTE]
    >  如果你更改当前登录的用户的组成员身份和组也是域的成员，可确保注销，并重新登录后所做的更改已完成。 如果您没有登录扩展/登录回原位，你可能会拒绝访问所新组成员身份不反映的当前登录名。  
  
## <a name="apply-the-configuration"></a>应用配置  
  
1.  在“BizTalk Server 配置”中，单击“应用配置”。  
  
2.  在“摘要”屏幕上，检查配置，然后单击“下一步”。  
  
3.  在“完成”屏幕上，单击“完成”。  
  
## <a name="import-configuration"></a>导入配置

> [!IMPORTANT]
> 当你导入配置文件时，确认配置文件不会配置尚未安装在要配置 BizTalk Server 的组件。 尝试配置 BizTalk Server 上不存在的组件可能造成死锁情况。 在此情况下，取消配置取决于配置文件正尝试进行配置的组件的组件。 但是，尝试取消配置依赖组件可能要求缺失的组件都存在并且配置。 若要解决此问题，必须编辑配置文件，以删除对已卸载的组件的引用，或将配置文件应用到兼容安装 BizTalk Server。  
> 
>  除非你已手动编辑文件导入的配置文件中不保存密码和备份文件位置。 如果已配置功能，是不导入它们。  
  
  
1.  在“BizTalk Server 配置”中，单击“导入配置”。  
  
2.  在“打开”对话框中，选择要导入的配置文件，然后单击“打开”。  
  
3.  在“BizTalk Server 配置”中，单击“应用配置”。  
  
4.  在“摘要”屏幕上，检查配置，然后单击“下一步”。  
  
5.  在“完成”屏幕上，单击“完成”。  

你可以导入使用 BizTalk Server 配置框架的 BizTalk Server 配置文件。 若要深入了解如何使用这些文件，请参阅[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)。  
  
## <a name="export-configuration"></a>导出配置

> [!NOTE]
>  配置文件中将不保存密码。    
 
1.  在“BizTalk Server 配置”中，单击“导出配置”。  
  
2.  在“另存为”对话框中，键入要保存的文件的名称，然后单击“保存”。  

 你可以导出使用 BizTalk Server 配置框架的 BizTalk Server 配置。 有关使用这些文件的详细信息，请参阅[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)  
  
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
  
## <a name="see-also"></a>另请参阅  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)   