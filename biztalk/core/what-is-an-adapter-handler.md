---
title: 一个适配器处理程序是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- handlers [adapters]
- adapters, handlers
- handlers [adapters], about handlers
ms.assetid: 4d1afa39-6320-467f-a7e8-f5f18236648e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8a1b60661427776dd4e35ffce27bf120bf94a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289301"
---
# <a name="what-is-an-adapter-handler"></a>一个适配器处理程序是什么？
适配器处理程序是适配器代码所运行的 BizTalk 主机的实例。 为适配器指定发送或接收处理程序，亦是指定适配器代码将在哪个主机实例的上下文环境中运行。 适配器处理程序负责执行适配器操作并包含特定适配器实例的属性。 默认的 BizTalk Server 配置将为所有安装的适配器创建适配器处理程序，但您可能希望创建其他适配器处理程序以实现负载平衡，或为特定的适配器处理程序提供进程隔离。  
  
 适配器处理程序绑定到 BizTalk 主机实例，而 BizTalk 主机实例又绑定到 BizTalk 服务器。 因此，若要在 Biztalk 服务器之间实现适配器处理的负载平衡，则必须向 BizTalk 组中添加其他 BizTalk 服务器。 如果要创建其他适配器处理程序以实现进程隔离，则无需向 BizTalk 组中添加其他 BizTalk 服务器。  
  
 如果需要创建新的主机实例以便在其中运行适配器处理程序，则必须首先创建主机，然后创建该主机的实例以运行 BizTalk 服务器之一。 有关详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)和[如何添加一个主机实例](../core/how-to-add-a-host-instance.md)。  
  
 必须将所有的适配器处理程序（除 HTTP 和 SOAP 适配器接收处理程序外）配置为在进程内主机中运行。 HTTP 和 SOAP 适配器接收处理程序只能运行于独立主机中。  
  
## <a name="see-also"></a>另请参阅  
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)