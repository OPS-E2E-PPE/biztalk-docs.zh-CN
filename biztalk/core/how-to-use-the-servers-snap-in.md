---
title: 如何使用服务器管理单元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f520692-9606-41f5-98ed-5a4962bd1f09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094bf6ac21aff4d65528db4ae105cb3081405210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383198"
---
# <a name="how-to-use-the-servers-snap-in"></a>如何使用服务器管理单元
此版本的企业单一登录 (SSO) 包括 ENTSSO 服务器管理单元中，以便您可以查看、 监视和通过 Windows 界面在 ENTSSO 服务器上执行某些操作。  
  
> [!NOTE]
>  如果您的系统具有防火墙且服务器名称使用 FQDN 格式，您可能无法联系服务器。 相反，必须指定 NetBIOS 名称或关联的 IP 地址。  
  
### <a name="to-use-the-entsso-servers-snap-in"></a>若要使用 ENTSSO 服务器管理单元  
  
1.  打开企业单一登录。  
  
2.  在作用域窗格中，单击**服务器**节点。  
  
     在结果窗格中显示以下信息。  
  
    -   **名称**：指定的名称。  
  
    -   **状态**：ENTSSO 服务 （联机、 脱机、 挂起、 启动、 停止、 启动挂起、 停止挂起） 的状态。  
  
    -   **日期**:获得信息的日期。  
  
    -   **时间**:获得信息的时间。  
  
    -   **SSO 服务器**:服务器的完全限定的名称。  
  
    -   **服务帐户**:ENTSSO 服务帐户。  
  
    -   **SSO 数据库**:与此服务器通信的 ENTSSO 数据库。  
  
    -   **密钥服务器**:指示密钥服务器模块是否正在运行。  
  
    -   **密码同步**:指示是否已安装密码同步。  
  
    -   **计算机**:计算机的 NETBIOS 名称。  
  
    -   **事件计数**:信息/警告/错误事件计数。 重置将计数器从 0 开始。  
  
    -   **安装的 SSO 版本**:ENTSSO.exe 的版本号。 此外指示这是否 (x86) 32 位或 64 位 (x64)。  
  
### <a name="to-start-or-stop-the-server-service"></a>若要启动或停止服务器服务  
  
-   在 ENTSSO 服务器管理单元中，右键单击服务器，然后单击**启动**或**停止**。  
  
### <a name="to-display-information-for-one-server"></a>若要显示的一台服务器的信息  
  
-   在服务器树中，单击服务器。  
  
     在结果窗格中显示的信息。  
  
### <a name="to-add-a-server"></a>若要添加服务器  
  
-   在作用域窗格中，右键单击，然后单击**添加服务器**。  
  
     **添加服务器**对话框随即出现。 键入或浏览到想要添加的服务器。  
  
> [!NOTE]
>  在某些工作组环境中，单击**浏览**按钮都将导致关闭此对话框。 而不是使用**浏览**按钮，只需在框中键入服务器名称。  
  
### <a name="to-view-or-change-server-properties"></a>查看或更改服务器属性  
  
-   在服务器树中，右键单击服务器，然后单击**属性**。  
  
     **服务器属性**对话框随即出现。 您可以查看或更改以下选项卡中的信息：  
  
    -   **审核级别**  
  
    -   **SSO 数据库**  
  
    -   **SSO 服务**  
  
    -   **密码同步**  
  
    -   **高级**