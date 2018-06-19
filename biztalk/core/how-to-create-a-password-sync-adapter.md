---
title: 如何创建密码同步适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa5bd13-efd9-4544-b5df-17d01c6ac5d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47381cc1ed71788673602c1db7eec5b5ac049ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249365"
---
# <a name="how-to-create-a-password-sync-adapter"></a>如何创建密码同步适配器
密码同步 (PS) 适配器是使用密码同步助手组件向企业单一登录 (SSO) 传递通知或从企业单一登录传递通知的应用程序。 请注意，虽然密码同步助手组件公开的是 COM 和 .NET Framework 接口，但适配器并不一定必须为 COM 组件。 可以将适配器设计为独立进程、COM+ 应用程序或 Windows 服务。  
  
### <a name="to-create-a-password-sync-adapter"></a>创建密码同步适配器  
  
1.  通知企业单一登录服务 (ENTSSO) 提供程序是活动使用`ISSOPSWrapper.InitializeAdapter`。  
  
     `InitializeAdapter`提供程序，通常进行调用，同一提供程序当前开启，且因此将通信从系统的密码更新通知 ENTSSO。 你还可以使用`InitializeAdapter`激活组适配器等资源。  
  
2.  通过将密码更新发送给 ENTSSO `ISSOPSWrapper.SendNotification`。  
  
     您必须确定如何从非 Windows 系统接收密码更新。 接收更新后，你可以将传递到 ENTSSO 使用信息`SendNotification`。 请注意，`SendNotification`并不局限于发送密码更新： 的体系结构`SendNotification`还可用于发送其他类型的通知。  
  
3.  通过使用从 ENTSSO 申请密码更新`ISSOPSWrapper.ReceiveNotification`。  
  
     由于密码同步适配器采用的是请求技术，因此 ENTSSO 永远也不会调用您的适配器。 相反，你的适配器定期调用`ReceiveNotification`若要查看是否有任何密码更新可用。 你可以选择在上设置等待标志`ReceiveNotification`。 设置 WAIT 会阻止该线程，直至有通知可用。  
  
     请注意，ENTSSO 使用纯文本格式向适配器传递密码更改。 适配器负责保护密码信息不致意外泄漏。 此外，适配器还要保护自身免遭其他无效源的欺骗或攻击，其中包括密码同步助手组件的欺骗。  
  
     通过 `pReceiveNotification` 参数从 ENTSSO 接收到密码更新之后，您必须将此信息传递到非 Windows 系统。 与`SendNotification`，必须确定与远程服务器通信的最佳方式。  
  
4.  关闭你适配器使用`ISSOPSWrapper.ShutdownAdapter`。  
  
     `ShutdownApplication`应为最后一个方法调用由适配器，并指示该适配器将不再发送或接收到 ENTSSO 的密码更新。  
  
     请注意，在关闭适配器后，ENTSSO 仍会缓存用户所做的所有密码更改，直到达到缓冲区大小限制。  
  
## <a name="see-also"></a>另请参阅  
 [使用企业单一登录进行编程](../core/programming-with-enterprise-single-sign-on.md)   
 [同步密码](../core/synchronizing-passwords.md)