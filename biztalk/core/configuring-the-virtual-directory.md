---
title: 配置虚拟目录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05f694744076f4242309ed58a70903fb7aaedbda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355150"
---
# <a name="configuring-the-virtual-directory"></a>配置虚拟目录
本主题介绍配置虚拟目录和验证用户的应用程序的过程。  
  
## <a name="configuring-the-directory"></a>配置目录  
  
#### <a name="to-configure-the-virtual-directory"></a>若要配置的虚拟目录  
  
1.  %Systemdrive%上创建一个文件夹以将配置为虚拟目录。  
  
2.  单击**启动**，依次指向**程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
3.  展开**\<服务器名称\>** ，然后展开**站点**。  
  
4.  右键单击**Default Web Site**然后单击**添加虚拟目录**。  
  
5.  在中**添加虚拟目录**对话框框中，键入别名。  
  
6.  键入在步骤 1 中创建的文件夹的路径。 此外，也可以单击 **（...）** 以浏览到文件夹位置。  
  
7.  单击“确定” 。 该文件夹将显示下**Default Web Site**文件夹。  
  
8.  右键单击该文件夹，然后单击**转换为应用程序**。  
  
9. 在中**添加应用程序**对话框中，单击**确定**。 该文件夹转换为应用程序 （您可以看到图标 – 从文件夹图标变为网站图标中的更改）。  
  
## <a name="verifying-an-application-for-a-user"></a>验证应用程序的用户  
 Internet 信息服务 (IIS) 应用程序运行在高度隔离;因此，必须验证该应用程序可以运行的 BizTalk Server Isolated Host Users 组中的用户上下文中使用以下过程。  
  
#### <a name="to-verify-an-application-for-a-user"></a>若要验证用户的应用程序  
  
1.  在控制面板中，打开**管理工具**，然后单击**组件服务**。  
  
2.  导航到中的 COM + 应用程序**组件服务**。  
  
3.  右键单击 COM + 应用程序，然后单击**属性**。  
  
4.  单击**标识**和更改此 COM + 应用程序运行是 BizTalk Server 组的成员的用户的标识。  
  
## <a name="see-also"></a>请参阅  
 [适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)