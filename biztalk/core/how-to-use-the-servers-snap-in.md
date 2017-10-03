---
title: "如何使用服务器管理单元 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f520692-9606-41f5-98ed-5a4962bd1f09
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12eb72323a6dcd1132f03febc9b4d9bd75316c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-servers-snap-in"></a>如何使用服务器管理单元
此版本的企业单一登录 (SSO) 包括 ENTSSO 服务器管理单元，您可用利用它通过 Windows 界面查看、监视 ENTSSO 服务器上的某些操作，以及在该服务器上执行某些操作。  
  
> [!NOTE]
>  如果系统具有防火墙且服务器名称使用的是 FQDN 格式，则可能无法与服务器取得联系。 因此，您必须指定 NetBIOS 名称或相关的 IP 地址。  
  
### <a name="to-use-the-entsso-servers-snap-in"></a>使用 ENTSSO 服务器管理单元  
  
1.  打开企业单一登录。  
  
2.  在作用域窗格中，单击**服务器**节点。  
  
     结果窗格中会显示的以下信息。  
  
    -   **名称**： 指定的名称。  
  
    -   **状态**: ENTSSO 服务 （联机状态，脱机，挂起、 启动、 停止、 启动挂起、 停止挂起） 的状态。  
  
    -   **日期**： 时获取信息的日期。  
  
    -   **时间**： 时获取信息的时间。  
  
    -   **SSO 服务器**： 服务器的完全限定的名称。  
  
    -   **服务帐户**: ENTSSO 服务帐户。  
  
    -   **SSO 数据库**: ENTSSO 数据库与此服务器通信。  
  
    -   **密钥服务器**： 指示是否正在运行的服务器模块。  
  
    -   **密码同步**： 指示是否安装了密码同步。  
  
    -   **计算机**： 计算机的 NETBIOS 名称。  
  
    -   **事件都统计**： 信息/警告/错误事件计数。 将其重置会使计数器从 0 开始计数。  
  
    -   **安装的 SSO 版本**: ENTSSO.exe 版本号。 此外指示这是 32 位 (x86) 还是 64 位 (x64)。  
  
### <a name="to-start-or-stop-the-server-service"></a>启动或停止服务器服务  
  
-   ENTSSO 服务器管理单元中，右键单击服务器，然后单击**启动**或**停止**。  
  
### <a name="to-display-information-for-one-server"></a>显示一个服务器的信息  
  
-   在服务器树中，单击该服务器。  
  
     信息将显示在结果窗格中。  
  
### <a name="to-add-a-server"></a>添加服务器  
  
-   在作用域窗格中，右键单击，然后单击**添加服务器**。  
  
     **添加服务器**对话框随即出现。 键入或浏览到要添加的服务器。  
  
> [!NOTE]
>  在某些工作组环境中，单击**浏览**按钮将导致关闭此对话框。 而不是使用**浏览**按钮，只需在框中键入服务器名称。  
  
### <a name="to-view-or-change-server-properties"></a>查看或更改服务器属性  
  
-   在服务器树中，右键单击服务器，然后单击**属性**。  
  
     **服务器属性**对话框随即出现。 您可以更改以下选项卡中的信息：  
  
    -   **审核级别**  
  
    -   **SSO 数据库**  
  
    -   **SSO 服务**  
  
    -   **密码同步**  
  
    -   **高级**