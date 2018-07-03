---
title: 使用 Office 365 Outlook 电子邮件适配器 |Microsoft Docs
description: 发送和接收消息在 BizTalk Server，包括电子邮件、 日历和联系人中使用 Office 365 Outlook 适配器概述
ms.custom: ''
ms.date: 06/19/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 2002ab6859a71a930ef9166f9b3a5a072ba77948
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946160"
---
# <a name="office-365-outlook-adapters-in-biztalk"></a>在 BizTalk 中的 office 365 Outlook 适配器

## <a name="overview"></a>概述
**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 3**，可以发送和接收 BizTalk Server 和 Office 365 Outlook 功能之间的消息。 功能包 3 中包括以下适配器：

- [Office 365 Outlook 电子邮件适配器](office365-mail-adapter.md)
- [Office 365 Outlook 日历适配器](office365-calendar-adapter.md)
- [Office 365 Outlook 联系人适配器](office365-contact-adapter.md)

## <a name="prerequisites"></a>必要條件

* 具有[Office 365 帐户](https://outlook.office365.com)
* 安装[功能包 3](https://aka.ms/bts2016fp3) BizTalk 服务器上
* 使用该帐户是 SSO Administrators 组的成员

## <a name="tms-overview"></a>TMS 概述

BizTalk Server TMS 是刷新 BizTalk 使用 Office 365 OAuth 令牌的服务。 它将刷新这些令牌定期，确保令牌始终保持有效。 它在企业单一登录服务 (ENT SSO) 上具有依赖关系，并必须承载在主密钥服务器的计算机上安装。 

## <a name="install-biztalk-server-tms"></a>安装 BizTalk Server TMS

1. 安装[功能包 3](https://aka.ms/bts2016fp3)。
2. 在`\Program Files (x86)\Microsoft BizTalk Server <your version>`，运行 BizTalkTMS.msi。
3. 输入用户名和密码是 SSO Administrators 组的成员的用户。 

![BizTalk Server TMS 安装程序](../core/media/BizTalk-TMS.png)

## <a name="sign-in-to-office-365"></a>登录到 Office 365

如果您要创建[发送端口](how-to-create-a-send-port2.md)或[接收位置](how-to-create-a-receive-location.md)在 BizTalk 管理，你可以**登录...** 到 Office 365 帐户：

  ![Office 365 登录](../core/media/office365-signin.png)

输入 Office 365 凭据，并确认权限。 这些凭据授权 BizTalk 要连接到并访问 Office 365 帐户。 在以下示例中，可以看到 Office 365 Outlook 日历的权限：

  ![Office 365 日历权限](../core/media/office365-calendar-permissions.png)

## <a name="get-started"></a>入门
安装 BizTalk Server TMS 后，你准备好创建这些项目中，并开始使用适配器：

- [Office 365 Outlook 电子邮件适配器](./office365-mail-adapter.md)
- [Office 365 Outlook 日历适配器](./office365-calendar-adapter.md)
- [Office 365 Outlook 联系人适配器](./office365-contact-adapter.md)
