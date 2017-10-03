---
title: "密码同步编程体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679edbf1-fb08-4472-b366-3e1d361b20e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb68af3624b19a5a5385902d6a0131cfe28acb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="password-sync-programming-architecture"></a>密码同步编程体系结构
密码同步适配器用于请求模型与企业单一登录系统的其余部分进行交互： 也就是说，该适配器主动接收密码更改从企业单一登录 (ENTSSO) 服务以及非 Windows 系统中。 同样，适配器会将从一个系统收到的密码更改推送至另一个系统。 与此模型中，你的适配器与三个体系结构组件进行交互： ENTSSO 体系结构、 密码同步 (PS) 帮助程序组件和指定的非 Windows 系统。  
  
## <a name="enterprise-single-sign-on-architecture"></a>企业单一登录结构  
 ENTSSO 是实现企业单一登录技术的服务，以本地服务的形式运行于适配器所在的同一系统上。 因此，适配器与 ENTSSO 之间的通信始终为本地通信。 但是，密码同步适配器与 ENTSSO 服务分别运行于不同的进程中。  
  
 ENTSSO 使用配置存储来存储适配器的配置信息。 配置存储应用程序的 Application Users 帐户与访问帐户相对应。 在适配器调用 ENTSSO 时，ENTSSO 将检查运行该适配器的帐户是否是为其配置的访问帐户。 该访问帐户必须为（本地或域）组帐户。  
  
 由于 ENTSSO 存储有适配器的相关信息，因此适配器可以通过自己的名称向 ENTSSO 标识自身。 适配器名称与用于存储适配器属性的配置存储应用程序名称和配置存储标识符相对应。 因此，适配器只需知道自己的适配器名称，就可在运行时访问配置信息并向 ENTSSO 系统正确地标识自身。  
  
## <a name="password-sync-helper"></a>密码同步助手  
 密码同步 (PS) 助手是 ENTSSO 提供的一个 COM 组件。 PS 助手与密码同步适配器运行于进程内，并公开 ISSOPSWrapper。 该适配器可以调用任一接口以与 ENTSSO 服务进行通信。 PS 助手与 ENTSSO 之间使用加密的（数据包保密性）轻量远程过程调用 (LRPC) 传递通信。 尽管此类通信主要用于密码更新，但您也可以使用接口在适配器与 ENTSSO 之间传递其他类型的通知。 由于 PS 助手在每个进程中以单一值的形式运行，多个适配器可以从同一适配器进程内调用同一 PS 助手。 有关以编程方式使用 PS 帮助器的详细信息，请参阅[同步密码](../core/synchronizing-passwords.md)。  
  
## <a name="non-windows-system"></a>非 Windows 系统  
 非 Windows 系统是适配器与之进行交互的远程计算机系统。 与非 Windows 系统进行交互的方式取决于您。  
  
## <a name="see-also"></a>另请参阅  
 [密码同步适配器](../core/password-sync-adapters.md)