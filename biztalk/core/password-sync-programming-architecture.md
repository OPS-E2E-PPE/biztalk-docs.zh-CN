---
title: 密码同步编程体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 679edbf1-fb08-4472-b366-3e1d361b20e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9da005574ef041eaa20582d02d1affd196963c81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394992"
---
# <a name="password-sync-programming-architecture"></a>密码同步编程体系结构
密码同步适配器使用拉模型与企业单一登录系统的其余部分进行交互： 即，该适配器主动接收密码更改从企业单一登录 (ENTSSO) 服务以及非 Windows 系统中。 同样，适配器将推送到另一个系统收到的密码更改。 与此模型中，您的适配器具有三个体系结构组件进行交互： ENTSSO 体系结构、 密码同步 (PS) 助手组件和指定的非 Windows 系统。  
  
## <a name="enterprise-single-sign-on-architecture"></a>企业单一登录体系结构  
 ENTSSO 是实现企业单一登录技术，并作为本地服务运行于适配器所在的同一系统上的服务。 因此，适配器与 ENTSSO 之间的通信始终是本地的。 但是，密码同步适配器从 ENTSSO 服务的单独进程中运行。  
  
 ENTSSO 使用配置存储来存储适配器的配置信息。 配置存储应用程序的应用程序用户帐户与访问帐户相对应。 当适配器调用 entsso 时，ENTSSO 将检查适配器为该适配器已配置的访问帐户中。 访问帐户必须是组的帐户 （本地或域） 帐户。  
  
 由于 ENTSSO 存储有关适配器的信息，该适配器可以向 ENTSSO 标识自身通过自己的名称。 适配器名称对应于配置存储应用程序名称和配置存储标识符，用于存储适配器属性。 因此，适配器必须知道只有自己的适配器名称以访问配置信息和正确地标识自身向 ENTSSO 系统在运行时。  
  
## <a name="password-sync-helper"></a>密码同步助手  
 密码同步 (PS) 助手是 ENTSSO 提供的一个 COM 组件。 PS 帮助程序以进程形式运行与密码同步适配器，并公开 ISSOPSWrapper。 该适配器可以调用任一接口与 ENTSSO 服务进行通信。 PS 助手传递通信与 entsso 之间使用加密 （数据包保密性） 轻量远程过程调用 (LRPC)。 尽管通信主要用于密码更新，但您可以使用接口的适配器和 ENTSSO 之间传递其他类型的通知。 由于 PS 助手在每个进程的单一实例值作为运行，就可以为多个适配器来调用同一 PS 助手对象从同一适配器进程内。 有关以编程方式使用 PS 助手的详细信息，请参阅[同步密码](../core/synchronizing-passwords.md)。  
  
## <a name="non-windows-system"></a>非 Windows 系统  
 非 Windows 系统是与您的适配器进行交互的远程计算机。 如何与非 Windows 系统进行交互是取决于您。  
  
## <a name="see-also"></a>请参阅  
 [密码同步适配器](../core/password-sync-adapters.md)