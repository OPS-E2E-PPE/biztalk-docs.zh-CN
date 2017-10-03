---
title: "配置虚拟目录 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a879fe776956c290fb895c7f0feb39b6088e268
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-virtual-directory"></a>配置虚拟目录
本主题演示了为用户配置虚拟目录并验证应用程序的过程。  
  
## <a name="configuring-the-directory"></a>配置目录  
  
#### <a name="to-configure-the-virtual-directory"></a>若要配置的虚拟目录  
  
1.  在 %systemdrive% 上，创建一个将配置为虚拟目录的文件夹。  
  
2.  单击**启动**，指向**程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
3.  展开**\<服务器名称 >**然后展开**站点**。  
  
4.  右键单击**Default Web Site**单击**添加虚拟目录**。  
  
5.  在**添加虚拟目录**对话框框中，键入别名。  
  
6.  键入在步骤 1 中创建的文件夹的路径。 或者，单击**（...）**以浏览到文件夹位置。  
  
7.  单击 **“确定”**。 该文件夹将显示下**Default Web Site**文件夹。  
  
8.  右键单击文件夹，然后单击**转换为应用程序**。  
  
9. 在**添加应用程序**对话框中，单击**确定**。 该文件夹将转换为应用程序（您可以看到图标的变化 – 从文件夹图标变为网站图标）。  
  
## <a name="verifying-an-application-for-a-user"></a>为用户验证应用程序  
 Internet 信息服务 (IIS) 应用程序在高度隔离的环境中运行；因此，必须使用以下过程验证应用程序是否可以在 BizTalk Server 独立主机用户组中的用户上下文中运行。  
  
#### <a name="to-verify-an-application-for-a-user"></a>若要验证用于用户的应用程序  
  
1.  在 Control Panel 中，打开**管理工具**，然后单击**组件服务**。  
  
2.  导航到中的 COM + 应用程序**组件服务**。  
  
3.  右键单击的 COM + 应用程序，然后单击**属性**。  
  
4.  单击**标识**和更改此 COM + 应用程序是 BizTalk Server 组的成员的用户在其下运行的标识。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on3.md)