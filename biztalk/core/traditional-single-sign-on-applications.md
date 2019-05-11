---
title: 传统的单一登录应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ffc09f49e6fecc1d6773a3b5ea8e89f8d98ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313327"
---
# <a name="traditional-single-sign-on-applications"></a>传统的单一登录应用程序
单一登录 (SSO) 编程体系结构包含一个映射组件的应用程序和用户、 要查找指定用途凭据的查找组件和管理组件来执行管理任务之间进行映射。 此外，SSO 还包含一个票证接口，以便你的应用程序可颁发和兑换票证。  
  
## <a name="mapping"></a>映射  
 映射是链接具有指定的应用程序的指定的用户的过程。 您可以关联应用程序和使用用户之间的映射`ISSOMapping`， `ISSOMapper`，和`ISSOMapper2`。 使用`ISSOMapping`，可以创建、 删除、 启用和禁用映射。 与`ISSOMapper`，和`ISSOMapper2`，可以获取并设置为当前用户的映射数据。  
  
## <a name="lookup"></a>查找  
 单一登录编程接口的核心是查找指定的用户凭据的功能。 您可以查看使用的凭据`ISSOLookup1`，和`ISSOLookup2`。 `ISSOLookup1`使用户能够检索其自己的外部凭据。 与此相反，`ISSOLookup2`还使您能够查找本地关联应用程序的远程用户的凭据。 前者是必需的传统上单一登录的应用程序，而后者时，可以编写一个主机启动的单一登录应用程序。  
  
## <a name="administration"></a>管理  
 你可以执行许多管理功能以编程方式通过`ISSOAdmin`， `ISSOAdmin2`，和`ISSOConfigStore`。 此类任务包括配置单一登录以及创建和描述为实现单一登录的应用程序。 此外可以创建和修改使用的 SSO 数据库`ISSOConfigDB`， `ISSOConfigOM`，和`ISSOConfigSS`。 最后，您可以管理使用的密码同步功能`ISSOPSAdmin`。  
  
## <a name="communication-and-ticketing"></a>通信和票证  
 你的应用程序将很可能需要发出消息，以便用户可以与远程应用程序进行通信。 若要更安全地与远程应用程序通信，必须颁发和兑换单一登录票证。 您还可以颁发和兑换票证以编程方式。  
  
## <a name="see-also"></a>请参阅  
 [单一登录应用程序](../core/single-sign-on-applications.md)