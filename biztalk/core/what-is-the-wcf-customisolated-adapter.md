---
title: WCF-CustomIsolated 适配器概述 | Microsoft Docs
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
ms.openlocfilehash: 2fdf5a646f586030df6c9492fc6fb2999e49527a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289693"
---
# <a name="what-is-the-wcf-customisolated-adapter"></a>WCF-CustomIsolated 适配器概述
通过 WCF-CustomIsolated 适配器，可将 BizTalk Server 中的 WCF 扩展性组件与独立主机配合使用。 该适配器为 WCF 框架赋予了完整的灵活性。 它允许用户选择并配置接收位置的 WCF 绑定，并指定终结点行为和安全设置。 该适配器仅可由 Internet 信息服务 (IIS) 中承载的传输使用。  
  
 WCF-CustomIsolated 适配器仅包含接收适配器。 使用 WCF-CustomIsolated 接收适配器，可通过为独立主机中运行的接收位置选择并配置的 WCF 绑定、服务行为、终结点行为、安全机制和入站消息正文来源接收 WCF 服务请求。 使用 WCF-CustomIsolated 接收适配器的接收位置可以配置为单向或请求-响应（双向）。  
  
 接收适配器有关 WCF 的详细信息，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF CustomIsolated 适配器](../core/configuring-the-wcf-customisolated-adapter.md)   
 [WCF 适配器](../core/wcf-adapters.md)