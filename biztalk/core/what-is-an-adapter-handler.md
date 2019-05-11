---
title: 适配器处理程序是什么？ | Microsoft Docs
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
ms.openlocfilehash: 09ef44c037b175497dfb6c1fb30ea9dd9fb0a43d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379691"
---
# <a name="what-is-an-adapter-handler"></a>适配器处理程序是什么？
适配器处理程序是适配器代码运行所在的 BizTalk 主机实例。 指定发送或接收适配器处理程序时您所指定的上下文中运行的适配器代码将在哪个主机实例。 适配器处理程序负责执行适配器并包含有关适配器的特定实例的属性。 默认的 BizTalk Server 配置将创建适配器处理程序的所有已安装的适配器，但您可能希望创建其他适配器处理程序以实现负载平衡，或提供特定的适配器处理程序的进程隔离。  
  
 适配器处理程序绑定到的 BizTalk 主机实例，和 BizTalk 主机实例又绑定到 BizTalk server。 因此，必须将其他 BizTalk 服务器添加到 BizTalk 组，如果你想要加载平衡适配器在 BizTalk 服务器处理。 不需要向 BizTalk 组中添加其他 BizTalk 服务器，如果要创建其他适配器处理程序以实现进程隔离。  
  
 如果需要创建新的主机实例运行适配器处理程序中的，您必须首先创建主机，然后创建一个 BizTalk 服务器上运行该主机的实例。 有关详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)并[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。  
  
 所有适配器处理程序，除了为 HTTP 和 SOAP 适配器接收处理程序必须都配置为在进程内主机中运行。 HTTP 和 SOAP 适配器接收处理程序只能在独立主机中运行。  
  
## <a name="see-also"></a>请参阅  
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)