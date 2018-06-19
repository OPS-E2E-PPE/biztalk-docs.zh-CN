---
title: 如何确定并设置为活动的事件写入者角色 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9fa663d395fc36205e137da374f17cb9470521
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249861"
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a>如何确定和设置活动的事件写入者角色
BAM 在写入活动事件时提供两种安全模式。 您可以授予写入单独活动的事件的权限，或者授予写入所有已部署活动上的事件的权限。  
  
 活动级别的安全性由您在部署某一 BAM 定义时创建的活动事件写入者角色提供。 例如，如果您为名为 CreditCard 的活动部署了一个定义，则 BAM 将创建一个名为 bam_CreditCard_EventWriter 的事件写入者角色。 该角色具有写入活动事件的权限。 若要授予某个用户写入活动事件的权限，您应该将该用户添加到该角色。  
  
 或者，您可以授予用户权限，以将它们添加到超级角色 BAM_EVENT_WRITER，有权写入所有活动 eve2nts 都写入所有活动。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，您必须具有以下各项：  
  
-   与部署该活动的 BAMPrimaryImportDb 的连接。  
  
-   对数据库的 DBO 权限。  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a>将用户添加到事件写入者角色  
  
1.  单击**启动**，指向**所有程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到 SQL Server**对话框中，选择 SQL Server 和适当的身份验证方法，，然后单击**连接**。  
  
3.  在**对象资源管理器**窗格中展开**数据库**，然后选择 BAM 主导入数据库。  
  
4.  单击**新查询**工具栏上的图标。  
  
5.  复制以下命令并将它们粘贴到查询窗口中。 使用适当的值替换域名、用户名和活动名称占位符。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  角色名称区分大小写。 活动名称也区分大小写，也就是说，它们必须匹配在部署活动时使用的大小写。  
  
6.  单击**执行**上工具栏或按 f5 键以运行命令的图标。  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a>将用户添加到事件写入者超级用户角色  
  
1.  单击**启动**，指向**所有程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到 SQL Server**对话框中，选择 SQL Server 和适当的身份验证方法，，然后单击**连接**。  
  
3.  在**对象资源管理器**窗格中展开**数据库**，然后选择 BAM 主导入数据库。  
  
4.  单击**新查询**工具栏上的图标。  
  
5.  复制以下命令并将它们粘贴到查询窗口中。 使用适当的值替换域名和用户名。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  角色名称区分大小写。 您必须按指示指定事件写入者角色。  
  
6.  单击**执行**上工具栏或按 f5 键以运行命令的图标。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 安全性](../core/managing-bam-security.md)