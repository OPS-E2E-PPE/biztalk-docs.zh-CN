---
title: 配置警报队列选项和通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0938ceed9adcf117bcc54433eff1e9d7cd06ab8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302123"
---
# <a name="configuring-alert-queue-options-and-notifications"></a>配置警报队列选项和通知
ESB 管理门户使用 ESB 警报服务生成警报，如错误消息到达时在门户中，并使用 ESB 通知服务进行排队，并将警报通知发送到订阅警报的用户。 可以编辑使用 ESB 管理门户中的这些服务的设置。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a>若要配置 ESB 警报服务的设置  
  
1.  请确保您登录到在门户中使用该帐户是 （门户管理员的自动成员） 的 Microsoft BizTalk Server Administrators 帐户组的成员。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**容错设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。  
  
3.  在中**警报队列选项**部分中，选择或清除**启用警报队列服务**复选框以启用或禁用服务。  
  
4.  如果启用该服务，编辑以满足我们的要求的其余控件中的值。 该服务与 Microsoft Active Directory 交互，因此你必须指定相应的 LDAP （轻型目录访问协议） 连接字符串。 此外可以指定队列批大小和轮询间隔。  
  
5.  单击**保存**以保存新设置。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a>若要配置 ESB 警报电子邮件通知服务的设置  
  
1.  请确保您登录到在门户中使用该帐户是 （门户管理员的自动成员） 的 BizTalk Server Administrators 帐户组的成员。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**容错设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。  
  
3.  在中**警报的电子邮件选项**部分中，选择或清除**启用警报电子邮件服务**复选框以启用或禁用服务。  
  
4.  如果启用该服务，编辑以满足我们的要求的其余控件中的值。 指定电子邮件服务器名称和"发件人"地址、 更改轮询间隔和批大小为必需的并指定该服务使用的可扩展样式表语言转换 (XSLT) 文件的路径。  
  
5.  单击**保存**以保存新设置。