---
title: 什么是 WCF CustomIsolated 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b60cc39092961703f45921c34a518f3da89691c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242790"
---
# <a name="what-is-the-wcf-customisolated-adapter"></a>什么是 WCF CustomIsolated 适配器？
Wcf-customisolated 适配器用于启用 BizTalk Server 中的 WCF 扩展性组件与独立主机配合使用。 该适配器能够完整 WCF 框架的灵活性。 它允许用户选择和配置 WCF 绑定的接收位置，并指定终结点行为和安全设置。 在 Internet 信息服务 (IIS) 承载的传输仅可以使用此适配器。  
  
 Wcf-customisolated 适配器由一个接收适配器组成。 通过 WCF 绑定、 服务行为、 终结点行为、 安全机制和入站的消息正文的选择和配置的源 Wcf-customisolated 接收适配器接收 WCF 服务请求使用的接收位置在独立主机中运行。 使用 Wcf-customisolated 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。  
  
 接收适配器的有关 WCF 的详细信息，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 Wcf-customisolated 适配器](../core/configuring-the-wcf-customisolated-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)