---
title: 如何创建密码同步适配器 |Microsoft Docs
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
ms.openlocfilehash: a2c3ca305f86f541bd1cb681ed97aea7768e77c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339932"
---
# <a name="how-to-create-a-password-sync-adapter"></a>如何创建密码同步适配器
密码同步 (PS) 适配器是使用密码同步助手组件传递通知到和从企业单一登录 (SSO) 的应用程序。 请注意，尽管 PS 助手组件公开的 COM 和.NET Framework 接口，您的适配器不会不一定必须是 COM 组件。 您可以设计您的适配器作为独立进程、 COM + 应用程序，或者 Windows 服务。  
  
### <a name="to-create-a-password-sync-adapter"></a>若要创建密码同步适配器  
  
1.  通知企业单一登录服务 (ENTSSO) 您的提供程序是活动使用`ISSOPSWrapper.InitializeAdapter`。  
  
     `InitializeAdapter` 通知 ENTSSO 提供程序，通常进行调用，同一提供程序当前已打开，并因此将通信从系统的密码更新。 此外可以使用`InitializeAdapter`激活其他资源，例如组适配器。  
  
2.  使用向 ENTSSO 发送密码更新`ISSOPSWrapper.SendNotification`。  
  
     您必须确定如何从非 Windows 系统接收密码更新。 接收到更新后，可以将传递到 entsso 之间使用的信息`SendNotification`。 请注意，`SendNotification`并不仅限于发送密码更新： 的体系结构`SendNotification`还可以发送其他类型的通知。  
  
3.  通过使用从 ENTSSO 请求密码更新`ISSOPSWrapper.ReceiveNotification`。  
  
     由于密码同步适配器的是请求技术，因此 ENTSSO 永远不会调用您的适配器。 相反，适配器定期调用`ReceiveNotification`以查看是否有可用的任何密码更新。 您可以选择对设置 WAIT 标志`ReceiveNotification`。 设置 WAIT 会阻止线程，直至有通知可用。  
  
     请注意 ENTSSO 到适配器以纯文本形式传递密码更改。 它负责保护密码信息不致意外泄漏的适配器。 它也是保护自身免遭欺骗的适配器的责任，或从其他无效源，包括密码同步助手组件的欺骗攻击。  
  
     从通过 ENTSSO 接收到密码更新之后`pReceiveNotification`参数，必须将此信息传递到非 Windows 系统。 与使用`SendNotification`，必须确定与远程服务器通信的最佳方式。  
  
4.  关闭适配器使用`ISSOPSWrapper.ShutdownAdapter`。  
  
     `ShutdownApplication` 应为最后一个方法由适配器调用，并指示该适配器将无法再发送或接收到 ENTSSO 密码更新。  
  
     请注意 ENTSSO 缓冲用户使适配器关闭的情况下，最多的缓冲区大小限制为任何密码更改。  
  
## <a name="see-also"></a>请参阅  
 [使用企业单一登录进行编程](../core/programming-with-enterprise-single-sign-on.md)   
 [同步密码](../core/synchronizing-passwords.md)