---
title: "配置警报队列选项和通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914af88b989c73444e16acedf43b9a236897859d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-alert-queue-options-and-notifications"></a>配置警报队列选项和通知
ESB 管理门户使用 ESB 警报服务来生成警报，如错误消息到达门户中，并使用 ESB 通知服务进行排队，并将警报通知发送到订阅警报的用户。 你可以编辑这些服务在 ESB 管理门户中使用的设置。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a>若要配置 ESB 警报服务的设置  
  
1.  确保您登录到门户使用的是 Microsoft BizTalk Server 管理员帐户 （其中门户管理员自动成员身份组） 的成员的帐户。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**错误设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。  
  
3.  在**警报队列选项**部分，选中或清除**启用警报队列服务**复选框以启用或禁用服务。  
  
4.  如果你启用该服务，编辑中的其余的控件，以满足我们的要求的值。 服务与 Microsoft Active Directory 交互，因此你必须指定相应的 LDAP （轻型目录访问协议） 连接字符串。 你还可以指定的队列批大小和轮询间隔。  
  
5.  单击**保存**以保存新的设置。  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a>若要配置 ESB 警报的电子邮件通知服务的设置  
  
1.  确保您登录到门户使用的 BizTalk Server 管理员帐户 （其中门户管理员自动成员身份组） 成员的帐户。  
  
2.  指向**管理员**在门户的主菜单上，选项卡，然后单击**错误设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。  
  
3.  在**警报的电子邮件选项**部分，选中或清除**启用警报电子邮件服务**复选框以启用或禁用服务。  
  
4.  如果你启用该服务，编辑中的其余的控件，以满足我们的要求的值。 指定电子邮件服务器名称和"发件人"地址、 更改轮询间隔和批处理大小根据需要，并指定服务使用的可扩展样式表语言转换 (XSLT) 文件的路径。  
  
5.  单击**保存**以保存新的设置。