---
title: 如何确定和设置活动的事件写入者角色 |Microsoft Docs
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
ms.openlocfilehash: fc3ff2fcc8ed4397db8d1eb8d5906cebd5c26af1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385262"
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a>如何确定和设置活动的事件写入者角色
BAM 在写入活动事件时提供两种安全模式。 您可以授予写入单独活动的事件的权限或您可以授予权限将事件写入上所有已部署的活动。  
  
 活动级别的安全性提供的部署 BAM 定义时创建的活动事件写入者角色。 例如，如果部署为 CreditCard 的活动的定义，则 BAM 将创建名为 bam_CreditCard_EventWriter 的事件写入者角色。 此角色具有写入活动事件的权限。 若要授予用户写入活动事件的权限，请向角色添加用户。  
  
 或者，可以授予用户权限，以便将它们添加到超级角色 BAM_EVENT_WRITER，有权写入所有活动 eve2nts 都写入所有活动。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，您必须：  
  
-   部署该活动的 bamprimaryimportdb 的连接。  
  
-   数据库的 DBO 权限。  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a>若要将用户添加到事件写入者角色  
  
1.  单击**启动**，依次指向**所有程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到 SQL Server**对话框中，选择 SQL Server 和相应的身份验证方法，然后单击**Connect**。  
  
3.  在中**对象资源管理器**窗格中展开**数据库**，然后选择 BAM 主导入数据库。  
  
4.  单击**新查询**工具栏上的图标。  
  
5.  复制以下命令并将其粘贴到查询窗口。 域名、 用户名和活动名称占位符替换为适当的值。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  角色名称是区分大小写。 活动名称也是区分大小写，也就是说，它们必须匹配部署活动时使用这种情况。  
  
6.  单击**Execute**按 f5 键以运行命令的工具栏上的图标。  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a>若要将用户添加到事件写入者超级角色  
  
1.  单击**启动**，依次指向**所有程序**，单击**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到 SQL Server**对话框中，选择 SQL Server 和相应的身份验证方法，然后单击**Connect**。  
  
3.  在中**对象资源管理器**窗格中展开**数据库**，然后选择 BAM 主导入数据库。  
  
4.  单击**新查询**工具栏上的图标。  
  
5.  复制以下命令并将其粘贴到查询窗口。 使用适当的值替换域名和用户名。  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  角色名称是区分大小写。 您必须指定为指定的事件写入者角色。  
  
6.  单击**Execute**按 f5 键以运行命令的工具栏上的图标。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 安全性](../core/managing-bam-security.md)