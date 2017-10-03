---
title: "传统单一登录在应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4396ecfab477fe1ae17b1abbb09ebf71c9bcb58c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="traditional-single-sign-on-applications"></a>传统单一登录在应用程序
单一登录 (SSO) 编程结构包含一个用于在应用程序和用户之间建立映射的映射组件、一个用于查找指定用途凭据的查找组件以及一个用于执行管理任务的管理组件。 此外，SSO 结构还包含一个票证接口，以便应用程序可颁发和兑换票证。  
  
## <a name="mapping"></a>映射  
 映射是将指定用户与指定应用程序相链接的过程。 你可以关联应用程序和利用的用户之间映射`ISSOMapping`， `ISSOMapper`，和`ISSOMapper2`。 与`ISSOMapping`，你可以创建、 删除、 启用和禁用映射。 使用 `ISSOMapper` 和 `ISSOMapper2`，您可以获取并设置当前用户的映射数据。  
  
## <a name="lookup"></a>查找  
 单一登录编程接口的核心是查找指定用户的凭据的功能。 您可以使用 `ISSOLookup1` 和 `ISSOLookup2` 查找凭据。 `ISSOLookup1` 使用户可以检索他们自己的外部凭据。 与此相反，`ISSOLookup2`还可用于查找本地关联应用程序的远程用户的凭据。 对于传统的单一登录应用程序，前者是必需的；而在编写主机启动的单一登录应用程序时，后者非常有用。  
  
## <a name="administration"></a>管理  
 你可以执行的许多管理功能以编程方式通过`ISSOAdmin`， `ISSOAdmin2`，和`ISSOConfigStore`。 此类任务包括配置单一登录以及对单一登录创建和描述应用程序。 此外可以创建和修改使用的 SSO 数据库`ISSOConfigDB`， `ISSOConfigOM`，和`ISSOConfigSS`。 最后，你可以管理使用的密码同步功能`ISSOPSAdmin`。  
  
## <a name="communication-and-ticketing"></a>通信和票证  
 您的应用程序很可能需要发出消息，以便用户能够与远程应用程序进行通信。 若要更安全地与远程应用程序进行通信，必须颁发和兑换单一登录票证。 您还可以通过编程方式颁发和兑换票证。  
  
## <a name="see-also"></a>另请参阅  
 [单一登录在应用程序](../core/single-sign-on-applications.md)