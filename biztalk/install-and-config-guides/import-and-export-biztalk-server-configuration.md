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
ms.openlocfilehash: 8677b05f06d54d61b07b8157bb425fb83c6d4c8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266190"
---
# <a name="import-and-export-biztalk-server-configuration"></a>导入和导出 BizTalk Server 配置
BizTalk Server 配置在本地计算机已安装的功能的配置状态提供高级分析。 该工具，可配置和取消对功能、 配置安全设置，并导入和导出配置。  
  
## <a name="prerequisites-to-use-the-biztalk-server-configuration"></a>使用 BizTalk Server 配置的先决条件  
   
-   以登录的帐户必须是本地管理员组的成员，并在 SQL Server 上拥有系统管理员权限。  
  
-   由 BizTalk Server 生成的 BizTalk 服务器配置中列出的默认帐户是本地组。 在多服务器环境中，用域组替换这些本地组。  
  
-   如果配置，以登录的帐户必须是 OLAP 计算机上的 OLAP Administrators 组的成员。  
  
    > [!NOTE]
    >  如果更改组成员身份的当前登录的用户，并且组也是域的成员，为确保注销，并完成所做的更改然后重新登录。 如果您没有登录扩展/登录回原位，您会被拒绝访问新的组成员身份不反映由当前登录名。  
  
## <a name="apply-the-configuration"></a>应用配置  
  
1.  在中**BizTalk Server 配置**，单击**应用配置**。  
  
2.  上**摘要**屏幕上，检查配置，并单击**下一步**。  
  
3.  上**完成**屏幕上，单击**完成**。  
  
## <a name="import-configuration"></a>导入配置

> [!IMPORTANT]
> 当您导入配置文件时，请确认配置文件不会配置未在您配置 BizTalk Server 安装的组件。 尝试配置 BizTalk Server 上不存在的组件可能会导致死锁情况。 在此情况下，取消对依赖的组件的配置文件尝试配置的组件。 但是，尝试取消对依存组件可能要求缺少的组件都存在并且配置。 若要解决此问题，必须编辑配置文件以删除对已卸载的组件的引用，或将配置文件应用到 BizTalk Server 的兼容安装。  
> 
>  除非您已手动编辑该文件导入的配置文件中不保存密码和备份文件位置。 如果已配置的功能，它们将不导入。  
  
  
1.  在中**BizTalk Server 配置**，单击**导入配置**。  
  
2.  在中**开放**对话框中，选择配置文件您想要导入，然后单击**打开**。  
  
3.  在中**BizTalk Server 配置**，单击**应用配置**。  
  
4.  上**摘要**屏幕上，检查配置，并单击**下一步**。  
  
5.  上**完成**屏幕上，单击**完成**。  

可以导入 BizTalk Server 使用 BizTalk Server 配置框架的配置文件。 有关使用这些文件的详细信息，请参阅[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)。  
  
## <a name="export-configuration"></a>导出配置

> [!NOTE]
>  密码不会保存到配置文件。    
 
1. 在中**BizTalk Server 配置**，单击**导出配置**。  
  
2. 在中**另存为**对话框中，键入该文件的名称要保存，然后单击**保存**。  

   您可以导出 BizTalk Server 配置使用 BizTalk Server 配置框架。 有关使用这些文件的详细信息，请参阅[使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)  
  
## <a name="unconfigure-features"></a>取消对功能  
 通过在 BizTalk Server 配置中删除它们，可以取消对 BizTalk Server 计算机上的功能。  
  
> [!NOTE]
>  取消对功能前，应先关闭 BizTalk Server 管理控制台。  
  
 
1.  在中**BizTalk Server 配置**，单击**取消对功能**。  
  
2.  在中**取消对功能**对话框中，选择你想要删除的功能，然后单击**确定**。  
  
    > [!NOTE]
    >  会出现一个对话框，警告您要取消对所选的功能。 单击“是”  继续。  
  
3.  上**摘要**屏幕上，检查配置，并单击**下一步**。  
  
4.  上**完成**屏幕上，单击**完成**。  
  
## <a name="update-databases"></a>更新数据库  
 您可以更改数据库服务器和 BizTalk Server 配置中编辑这些实体，与 BizTalk Server 功能相关联的数据库。  
  
> [!NOTE]
>  配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 SQL Server 默认支持实例和命名的实例。  
> 
>  此工具允许批量编辑数据库。  
  
 
1.  在中**BizTalk Server 配置**，单击**视图**，然后单击**数据库。**  
  
2.  在中**数据库**对话框中，选择你想要编辑的功能，然后单击**编辑**。  
  
3.  在中**数据库**对话框中，键入数据库服务器名称和数据库的名称是想要使用，然后单击**确定**。  
  
4.  在中**数据库**对话框中，单击**关闭**。  
  
## <a name="update-service-accounts"></a>更新服务帐户  
 你可以通过 BizTalk Server 配置中编辑这些实体与 BizTalk Server 功能相关联的服务帐户。  
  
> [!NOTE]
>  此工具允许批量编辑帐户。  
  
1.  在中**BizTalk Server 配置**，单击**视图**，然后单击**服务帐户**。  
  
2.  在中**服务帐户**对话框中，选择你想要编辑的功能，然后单击**编辑**。  
  
3.  在中**用户凭据**对话框框中，键入用户名和密码，你想要使用，然后单击**确定**。  
  
4.  在中**服务帐户**对话框中，单击**关闭**。  
  
## <a name="see-also"></a>请参阅  
 [配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [使用配置框架](../install-and-config-guides/working-with-the-configuration-framework.md)   