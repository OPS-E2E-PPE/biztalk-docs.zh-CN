---
title: 配置 SSO 票证 |Microsoft Docs
description: 使用 SSO 管理或命令行来允许和验证企业单一登录票证系统级别和 BizTalk Server 中的关联应用程序。
ms.custom: ''
ms.date: 01/08/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ce6c1de1a94225f06d09b66cc3e6c60c471f24
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443370"
---
# <a name="configure-the-sso-tickets-in-biztalk-server"></a>在 BizTalk Server 中配置 SSO 票证
整个单一登录系统，可以使用企业单一登录 (SSO) 管理 MMC 或命令行对票证行为进行控制。 使用此工具，可以允许使用票证，并验证 SSO 票证。  
  
## <a name="before-you-begin"></a>开始之前

- 如果在远程计算机上安装 SSO 管理，则可以运行远程[IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method)操作。 SSO 管理模块和运行时模块 （ENTSSO 服务） 之间的所有通信进行都加密。  
  
- 使用 ssomanage.exe 命令行实用工具，可以输入在关联应用程序级别的票证超时值。 仅当创建的应用程序时不进行应用程序的更新时，才可以执行此操作。
  
- 只有 SSO 管理员组中的用户可以在 SSO 系统级别和关联应用程序级别配置票证。  
  
- 如果在系统级别禁用了票证，它不能在关联应用程序级别使用它。 就可以启用系统级别票证和关联应用程序级别禁用它们。  
  
- 如果在系统级别启用验证，则必须在关联应用程序级别验证票证。 它是可以禁用在系统级别的验证并启用关联应用程序级别。  
  
- 如果在系统级别和关联应用程序级别输入票证超时，则在关联应用程序级别输入确定票证到期时间。  
  
有关票证和票证验证的详细信息，请参阅[SSO 票证](../core/sso-tickets.md)。  
  
## <a name="allow-affiliate-application-tickets-using-sso-administration"></a>允许使用 SSO 管理关联应用程序票证  
  
1.  从**启动**菜单中，选择**所有程序** > **Microsoft 企业单一登录** > **SSO 管理**.
  
2.  中的 ENTSSO Mmc 管理单元的作用域窗格中，展开**关联应用程序**节点。  
  
3.  右键单击**关联应用程序** > **属性**。  
  
4.  选择**选项**选项卡。  
  
5.  选择**允许使用票证**并输入所需的票证超时值。  
  
## <a name="allow-and-validate-sso-system-level-tickets-using-the-command-line"></a>允许并验证 SSO 系统级别票证使用命令行  
  
1. 打开命令提示符 (开始菜单 > 类型**命令提示符**> 选择**命令提示符下**)。

    > [!TIP]
    >  在系统上支持用户帐户控制 (UAC)，您可能需要使用管理权限打开命令提示符 (右键单击**命令提示符下**> * * 以管理员身份运行)。
  
2. 在命令行上，转至企业单一登录安装目录。 默认安装目录是`\Program Files\Common Files\Enterprise Single Sign-On`。 例如，输入： 

    `cd C:\Program Files\Common Files\Enterprise Single Sign-On`
  
3. 类型`ssomanage -tickets <allowed yes/no> <validate yes/no>`，其中*\<允许是/否\>* 指示对于票证是否允许或不是，和*\<验证是/否\>* 指示是否需要进行验证后他们正在兑换票证。  
  
    可以使用`yes`， `no`， `on`，或`off`允许和/或验证票证。 这些词不区分大小写，必须在任何语言设置下都能使用。
  
## <a name="see-also"></a>请参阅

[了解 SSO](../core/understanding-sso.md)   
[使用 SSO](../core/using-sso.md)
